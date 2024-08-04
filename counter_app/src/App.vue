<template>
<main>
  <div class="container">
    <h2>Counter App</h2>
  <p>count : {{count}}</p>
<button class="btn-primary" @click="increase">increase</button>
<br>
<button class="btn-primary" @click="decrease">decrease</button>
<br>
<button class="btn-primary" @click="reset">reset</button>
  </div>
</main>
</template>

<script>
export default {
  name: 'App',
  data(){
    return {
        count:0
      }
  },
  methods: {
    increase(){
      this.count++;
    },
    decrease(){
      this.count--;
    },
    reset(){
      this.count=0
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
