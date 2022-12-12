<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <router-view />
  <p>Counter: {{ numClicks }}</p>
  <button v-on:click="sumaClicks()">Clicke Me</button>
  <button v-on:click="restaClicks()">Resta Clicks</button>
  <div>
    <h3> Shop </h3>
    <ul v-if="numClicks > 20"  v-on:click="improvement1()"> {{ shop[0].name}}</ul>
    <ul v-if="numClicks > 40"  v-on:click="improvement2()"> {{ shop[1].name}}</ul>
  </div>
 
</template>

<script>
export default {
  name: "App",
  props: {},
  data() {
    return {
      numClicks: 0,
      earnings: null,
      date: null,
      seconds: null,
      shop: [{
        name: "Improvement 1",
        level: 1,
        initialCost: 4
      },
      {
        name: "Improvement 2",
        level: 2,
        initialCost: 10
      }
    ],
    };
  },
  computed: {},
  methods: {
    sumaClicks() {
      // return this.numClicks = this.num_clicks + 1
      return this.numClicks++;
    },
    restaClicks() {
      // console.log("test")
      return this.numClicks--;
    },
    improvement1() {
      this.numClicks = this.numClicks - this.shop[0].initialCost; // Substract clicks of initialCost 
      this.shop[0].initialCost = this.shop[0].initialCost * 2; // Multiply by 2 initialCost
      // Add 1 click every 30 seconds
      setInterval(this.sumaClicks, 30000) // Execute sumaClicks() every 30 seconds
      return this.numClicks 
    },
    improvement2() {
      this.numClicks = this.numClicks - this.shop[1].initialCost; // Substract clicks of initialCost 
      this.shop[1].initialCost = this.shop[1].initialCost * 2; // Multiply by 2 initialCost
      console.log(this.shop[1].initialCost)
      return this.numClicks 
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
