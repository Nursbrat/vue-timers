<template>
  <div class="timer-plus">
    <div class="plus-wrapper">
      <div class="plus-horizontal"></div>
      <div class="plus-vertical"></div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'TimerPlusButton',
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .timer-plus {
    display: flex;
    width: 225px;
    height: 120px;
    left: 212px;
    top: 72px;
    background: #696969;
    /* margin-bottom: 45px; */
    align-items: center;
    justify-content: center;
  }

  .timer-plus:hover {
    cursor: pointer;
  }

  .plus-wrapper {
    height: 20px;
    width: 20px;
  }

  .plus-horizontal {
    width: 20px;
    height: 3px;
    background: #9E9E9E;
    position: absolute;
    margin-top: 9px;
  }

  .plus-vertical {
    width: 3px;
    height: 20px;
    position: absolute;
    margin-left: 9px;
    background: #9E9E9E;
  }

</style>
