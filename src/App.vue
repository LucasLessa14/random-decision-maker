<template>
  <div id="app">
    <div class="header">
      <p>Gerador de números aleatório para tomadas de decisões ao acaso</p>
    </div>

    <div class="form">
      <label for="max-number">Digite o maior número</label>
      <input type="number" name="max-number" id="max-number" placeholder="Maior número" v-model="max">
      <label for="min-number">Digite o menor número</label>
      <input type="number" name="min-number" id="min-number" placeholder="Menor número" v-model="min">
      <button class="btn" @click="gerar">Gerar</button>
    </div>

    <div v-if="showResult" class="result">
      <p>Número aleatório gerado: {{ randomNumber }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      max: 5,
      min: 0,
      randomNumber: 0,
      showResult: false
    }
  },
  methods: {
    gerar() {
      if (!this.showResult) this.showResult = true;
      this.randomNumber = parseInt(this.min) + Math.floor((this.max - this.min + 1) * Math.random());
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: #F7F6F3;
  font-family: 'Josefin Sans', sans-serif;
}

#app {
  height: 100vh;
  width: 100vw;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
}

.header {
  width: 80%;
  max-width: 496px;
  font-size: 24px;
  text-align: center;
  margin-bottom: 32px;
}

.form {
  width: 90%;
  max-width: 496px;
  background-color: #fff;
  border-radius: 20px;
  padding: 32px 16px;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  flex-direction: column;
}

label {
  margin-top: 32px;
  margin-bottom: 16px;
}

input[type=number] {
  width: 100%;
  height: 48px;
  border-radius: 8px;
  border: 1px solid #722196;
  padding: 0 8px;
}

/* Chrome, Safari, Edge, Opera */
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

/* Firefox */
input[type=number] {
  -moz-appearance: textfield;
}

input[type=number]:focus {
  outline: none;
  box-shadow: none;
}

.btn {
  background: linear-gradient(135deg, #500870 0%, #A31564 100%);
  border-radius: 8px;
  width: 100%;
  height: 48px;
  border: none;
  color: #fff;
  font-size: 24px;
  margin-top: 32px;
}

.btn:focus {
  outline: none;
  box-shadow: none;
}

.result {
  margin-top: 32px;
}
</style>
