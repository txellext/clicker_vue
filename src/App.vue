<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <router-view />
  <p>Counter: {{ num_clicks }}</p>
  <p>Earnings: {{ earnings }}</p>
  <button v-on:click="sumClicks()">Clicke Me</button>
  <button v-on:click="restClicks()">Resta Clicks</button>
  <p v-on:click="improvement()">Buy</p>
</template>

<script>
export default {
  name: "App",
  props: {},
  data() {
    return {
      num_clicks: 0,
      earnings: null,
      shop: [{
        name: "mejora 1",
        level: 1,
        initialCost: 4
      }
    ],
    };
  },
  computed: {},
  methods: {
    sumClicks() {
      // return this.num_clicks = this.num_clicks + 1
      return this.num_clicks++;
    },
    restClicks() {
      // console.log("test")
      return this.num_clicks--;
    },
    improvement() {
      
      console.log(this.shop[0])
      
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
