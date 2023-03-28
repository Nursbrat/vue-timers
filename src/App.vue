<script setup>
import TimersGrid from './components/TimersGrid.vue';



</script>

<template>
  <div class="timers-wrapper">
    <TimersGrid />
  </div>
</template>

<style scoped>
body {
  background: #353638;
  padding: 0px;
  margin: 0px;
}

.timers-wrapper {
  display: flex;
  flex-wrap: wrap;
  row-gap: 45px;
  column-gap: 50px;
  padding: 72px 53px;
  justify-content: flex-start;
  align-items: center;
}

@media (min-width: 880px) {
  .timers-wrapper {
    max-width: 775px;
  }

}

@media (min-width: 605px) and (max-width: 879px) {
  .timers-wrapper {
    max-width: 275px;
  }
}

@media (max-width: 604px) {
  .timers-wrapper {
    max-width: 225px;
  }
}
</style>
