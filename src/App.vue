<template>
  <div id="app">
    <div class="main">
      <BaseCard v-for="(v, i) in values" :key="i" :number= "v" :symbol="currentSymbol"></BaseCard>
      <div class="butSymbol">
        <button @click="changeSymbol">CAMBIAR PALO</button>
      </div>
    </div>
  </div>
</template>

<script>
import BaseCard from './components/BaseCard'

export default {
  name: 'app',
  components: {
    BaseCard
  },
  data () {
    return {
      values: ['A', '2', '3', '4', '5', '6',
        '7', '8', '9', '10', 'J', 'Q', 'K'],
      symbols: ['♠', '♥', '♦', '♣'],
      currentSymbol: '♠'
    }
  },
  methods: {
    changeSymbol () {
      let currentIndex = this.symbols.indexOf(this.currentSymbol)
      const nextIndex = currentIndex === this.symbols.length - 1 ? 0 : currentIndex += 1
      this.currentSymbol = this.symbols[nextIndex]
      return this.currentSymbol
    }
  }
}
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  .butSymbol {
    width: 230px;
    margin-top: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  button {
    height: 150px;
    width: 180px;
    font-size: 30px;
    font-family: monospace;
    cursor: pointer;
    border-radius: 10%;
    box-shadow: 0px 0px 5px 5px;
    background: yellowgreen;
  }

  button:hover {
    background: rgb(162, 218, 51);
  }

  .main {
    margin: auto;
    display: flex;
    width: 600px;
    flex-wrap: wrap;
  }

  .cards {
    border: 5px solid black;
    margin: auto;
    width: 400px;
    display: flex;
    flex-wrap: wrap;
    padding: 20px;
    margin: 5px;
  }
</style>
