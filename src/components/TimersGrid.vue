<template>
    <div v-for="(_, index) in timers" :key="index">
        <Timer />
    </div>
    <AddTimer @click="addTimer" />
</template>
  
<script>
import Timer from '../components/Timer.vue';
import AddTimer from '../components/AddTimer.vue';

import { ref } from 'vue';

export default {
    name: 'TimerGrid',
    components: {
        Timer,
        AddTimer
    },
    setup() {
        const timers = ref([1]);

        function addTimer() {
            timers.value.push(1);
        }

        return {
            timers,
            addTimer,
        };
    },
};
</script>
  
<style ></style>
  