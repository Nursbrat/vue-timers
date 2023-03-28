<template>
  <Timer v-for="index in children" :key="index"></Timer>
  <TimerPlus @click="add"/>
</template>

<script>
  import Timer from './Timer.vue'
  import TimerPlus from './Timer-plus.vue'

  export default {
    name: 'TimersComponent',
    
    components: {
      Timer,
      TimerPlus
    },

    data() {
      return {
        children: [Timer],
      }
    },

    methods: {
      add() {
        this.children.push(Timer);
      }
    },

    mounted() {
      // console.debug(this);
    }
  }
</script>