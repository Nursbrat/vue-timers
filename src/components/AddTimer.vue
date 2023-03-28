<template>
    <div class="timer-plus">
        <button class="plus-wrapper">
            <img src="../assets/plus.svg" alt="plus">
        </button>
    </div>
</template>
  
<script>
export default {
    name: 'AddTimer',
}
</script>
  
<style >
.timer-plus {
    display: grid;
    align-items: center;
    justify-content: center;
    width: 225px;
    height: 120px;
    left: 212px;
    top: 72px;
    background: #696969;
    cursor: pointer;

}



.plus-wrapper {
    display: grid;
    place-content: center;
    height: 20px;
    width: 20px;
}


</style>
  