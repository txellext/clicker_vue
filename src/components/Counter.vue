<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      Let's try our awesome clicker
    </p>
  </div>
</template>



<script>
export default {
  name: 'Counter',
  props: {
    msg: String
  }
}
</script>



<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
