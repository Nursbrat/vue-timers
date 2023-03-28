<template>
  <div class="timer">
    <div class="timer__numbers" :class="{ active: timerActive }"> {{ formattedTime }}</div>
    <div class="timer__buttons" :class="{ active: !timerActive }">
      <button v-if="!timerActive" @click="startTimer"><img src="../assets/start.svg" alt="start"></button>
      <button v-else @click="pauseTimer"><img src="../assets/pause.svg" alt="pause"></button>
      <button @click="resetTimer">
        <img src="../assets/reset.svg" alt="reset" v-if="timerActive">
        <img src="../assets/resetstop.svg" alt="resetstop" v-else>
      </button>
    </div>

  </div>
</template>
  
<script>

import { ref, computed, watch } from 'vue';

export default {
  name: 'TimeCounter',
  setup() {
    const timer = ref(null);
    const startTime = ref(0);
    const elapsedTime = ref(0);
    const timerActive = computed(() => timer.value !== null);
    const formattedTime = computed(() => formatTime(elapsedTime.value));

    function startTimer() {
      startTime.value = Date.now() - elapsedTime.value;
      timer.value = setInterval(() => {
        elapsedTime.value = Date.now() - startTime.value;
      }, 10);
    }

    function pauseTimer() {
      clearInterval(timer.value);
      timer.value = null;

    }

    function resetTimer() {
      clearInterval(timer.value);
      timer.value = null;
      startTime.value = 0;
      elapsedTime.value = 0;

    }

    function formatTime(time) {
      const hours = Math.floor(time / 3600000)
      const minutes = Math.floor(time / 60000);
      const seconds = Math.floor((time % 60000) / 1000);
      if (hours) return `${hours.toString().padStart(2, '0')}:${minutes.toString().padStart(2, '0')}:${seconds
        .toString()
        .padStart(2, '0')}`;
      if (minutes) return `${minutes.toString().padStart(2, '0')}:${seconds
        .toString()
        .padStart(2, '0')}`;
      return `${seconds
        .toString()
        .padStart(2, '0')}`;
    }

    watch(timerActive, (isActive) => {
      if (!isActive) {
        startTime.value = 0;
      }
    });

    return {
      startTimer,
      pauseTimer,
      resetTimer,
      formattedTime,
      timerActive,
    };
  },
};
</script>

<style>
.timer {
  display: grid;
  width: 225px;
  height: 120px;
  background: #696969;
  font-family: 'Gotham Pro';
  font-style: normal;
  font-weight: 400;
  font-size: 22px;
  line-height: 21px;
  text-align: center;


}

.timer__numbers {
  display: grid;
  place-content: center;
  font-family: 'Gotham Pro';
  font-style: normal;
  font-weight: 400;
  font-size: 22px;
  line-height: 21px;
  text-align: center;
  color: #9E9E9E;
}

.timer__numbers.active {
  color: #FFFFFF;
}

.timer__buttons {
  display: grid;
  grid-template-areas: "b b";
  border-top: 1px solid #FFFFFF;
}

.timer__buttons.active {
  border-top: 1px solid #9E9E9E;
}
</style>
  