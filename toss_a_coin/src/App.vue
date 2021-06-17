<template>
  <div class="coin_container">
  <div class="coin" v-for="(coin, index) in status" :key='index'><P>{{coin}}</P></div>
  </div>
  <button @click="toss">TOSS</button>
  <button @click="add">Add Coin</button>
  <button @click="remove">Remove Coin</button>
</template>


<script>
export default {
  name: 'App',
  data() {
    return {
      status: ['H']
    }
  },
  methods: {
    toss(){
      const hOrt = 'HT';
      for (let i in this.status) {
        this.status[i] = hOrt[Math.floor(Math.random()*2)];
      }
    },
    add(){
      this.status.push('H');
    },
    remove (){
      this.status.pop();
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


.coin{
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: blanchedalmond;
  width: 3rem;
  height: 3rem;
  border-radius: 1.5rem;
  margin: 0.2rem;
}
.coin p {
  font-weight: bold;
  color:brown;
}
.coin_container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 1rem;
}


</style>
