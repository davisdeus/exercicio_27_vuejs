<script>
export default {

  data() {
    return {
      num1: 0,
      num2: 0,
      operacao: '+',
      resul: 0
    }
  },

  methods: {
    soma() {
      if (this.operacao === '+') {
        this.resul = parseInt(this.num1) + parseInt(this.num2);
      } else if (this.operacao === '-') {
        this.resul = parseInt(this.num1) - parseInt(this.num2);
      } else if (this.operacao === '*') {
        this.resul = parseInt(this.num1) * parseInt(this.num2);
      } else if (this.operacao === '/') {
        this.resul = parseInt(this.num1) / parseInt(this.num2);
      } else {
        // Caso a operação não seja válida
        this.resultado = 'Operação inválida';
      }
    }
  }

}
</script>

<template>

  <body>
    <div class="container">
      <h1>Calculadora Aritmetrica</h1>
      <div class="calcular">
        <input type="number" v-model.number="num1" @input="soma">
        <input type="number" v-model.number="num2" @input="soma">
        <br>
        <select v-model="operacao" @change="soma">
          <option value="+">+</option>
          <option value="-">-</option>
          <option value="*">*</option>
          <option value="/">/</option>
        </select>
      </div>
      <p>Resultado: {{ resul }}</p>

    </div>
  </body>
</template>

<style scoped>
  .container {
    display:block ;
    font-family: sans-serif;
    font-weight: bold;
    margin-top: 100px;
    background-color: #EFFBF8;
    width: 30%;
    padding: 40px 25px 40px 25px;
    border-radius: 15px;
    border:2px solid black;
  }
  input {
    border-radius: 5px;
    margin: 5px 10px  5px 0;
    padding: 5px;
  }
  select {
    border-radius: 5px;
    padding: 5px;
    margin: 5px 10px 5px 0;
  }
</style>
