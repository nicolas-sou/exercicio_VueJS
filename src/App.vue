<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: 'mais',
      result: 0,
    };
  },
  methods: {
    calculadora() {
      switch (this.operation) {
        case 'mais':
          this.result = this.num1 + this.num2;
          break;
        case 'subtrair':
          this.result = this.num1 - this.num2;
          break;
        case 'multiplicar':
          this.result = this.num1 * this.num2;
          break;
        case 'dividir':
          this.result = this.num1 / this.num2;
          break;
      }
    },
  },
};
</script>

<template>
  <h1 class="titulo">Calculadora aritmética</h1>
  <h2 class="subtitulo">Insira seu número desejado:</h2>
  <div class="calculadora">
    <div class="campos">
      <input v-model.number="num1" type="number" @input="calculadora">
      <input v-model.number="num2" type="number" @input="calculadora">
      <select v-model="operation" @change="calculadora">
        <option value="mais">+</option>
        <option value="subtrair">-</option>
        <option value="multiplicar">*</option>
        <option value="dividir">/</option>
      </select>
    </div>
    <div class="resultado">
      <h3>Resultado: {{ result }}</h3>
    </div>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: sans-serif;
}

body {
  background-color: #41ba8323;
}

.titulo {
  padding: 30px;
  text-align: center;
  background-color: #41ba84;
  color: #f0f0f0;
}

.subtitulo {
  text-align: center;
  font-size: 20px;
  margin-top: 80px;
}

.calculadora {
  display: grid;
  margin-top: 20px;
  align-content: center;
  justify-items: start;
  justify-content: center;
}

.campos {
  margin-bottom: 20px;
}

.campos input,
.campos select {
  display: block;
  padding: 10px;
  font-size: 20px;
  border-radius: 10px;
  border: 1px solid #ccc;
  margin-top: 20px;
}

.resultado {
  background-color: #41ba84;
  color: #fff;
  padding: 13px;
  border-radius: 5px;
  width: 100%;
  text-align: center;
}

h3 {
  margin: 0;
}
</style>