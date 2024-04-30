<template>
  <div class="calculator">
    <h1>Calculadora Aritmética</h1>
    <div>
      <input type="number" v-model="numero1" @input="calcularResultado">
      <select v-model="operacao" @change="calcularResultado">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input type="number" v-model="numero2" @input="calcularResultado">
    </div>
    <div>
      <h2>Resultado: {{ resultado }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: '+',
      resultado: 0
    }
  },
  methods: {
    calcularResultado() {
      switch (this.operacao) {
        case '+':
          this.resultado = parseFloat(this.numero1) + parseFloat(this.numero2);
          break;
        case '-':
          this.resultado = parseFloat(this.numero1) - parseFloat(this.numero2);
          break;
        case '*':
          this.resultado = parseFloat(this.numero1) * parseFloat(this.numero2);
          break;
        case '/':
          this.resultado = parseFloat(this.numero1) / parseFloat(this.numero2);
          break;
        default:
          this.resultado = 0;
      }
    }
  }
}
</script>

<style>
.calculator {
  max-width: 400px;
  margin: auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

input, select {
  margin: 5px;
  padding: 5px;
}

h2 {
  margin-top: 20px;
}
</style>
