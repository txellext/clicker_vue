<template>
  <div class="home">
    <Counter msg="Welcome to my Clicker App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import Counter from '@/components/Counter.vue'

export default {
  name: 'HomeView',
  components: {
    Counter
  }
}
</script>
