<template>
  <div class="card">
    <div class="number">{{ number }}</div>
    <div class="symbol">{{ symbol }}</div>
  </div>
</template>

<script>
export default {
  name: 'BaseCard',
  props: {
    number: String,
    symbol: String
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Monoton&display=swap');

  .card {
    margin: 5px;
    width: 100px;
    height: 150px;
    background: linear-gradient(red 50%, black 50%);
    border: 5px solid black;
    display: grid;
    grid-template-rows: repeat(2, 50%);
    justify-content: space-around;
    align-items: center;
    box-shadow: 7px 7px 2px 2px;
    padding: 5px 0px 5px 0px;
  }

  .number, .symbol {
    font-size: 50px;
    color: white;
    font-family: 'Monoton';
  }

  .symbol {
    font-size: 70px;
  }
</style>
