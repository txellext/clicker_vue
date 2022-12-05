<template>
  <div class="home">
    <CounterClicks msg="Welcome to my Clicker App"/>
  </div>
</template>

<script>
import CounterClicks from '/src/components/CounterClicks.vue'

export default {
  name: 'HomeView',
  components: {
    CounterClicks
  }
}
</script>
