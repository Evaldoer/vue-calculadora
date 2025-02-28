<template>
    <div class="calculator">
      <input type="number" v-model.number="number1" placeholder="Primeiro número" />
      <input type="number" v-model.number="number2" placeholder="Segundo número" />
      <select v-model="operation">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">*</option>
        <option value="divide">/</option>
      </select>
      <p>Resultado: {{ result }}</p>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ArithmeticCalculator',
    data() {
      return {
        number1: 0,
        number2: 0,
        operation: 'add'
      };
    },
    computed: {
      result() {
        const num1 = parseFloat(this.number1) || 0;
        const num2 = parseFloat(this.number2) || 0;
  
        switch (this.operation) {
          case 'add':
            return num1 + num2;
          case 'subtract':
            return num1 - num2;
          case 'multiply':
            return num1 * num2;
          case 'divide':
            return num2 !== 0 ? num1 / num2 : 'Erro: Divisão por zero';
          default:
            return 0;
        }
      }
    }
  };
  </script>
  
  <style scoped>
  .calculator {
    max-width: 300px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }
  </style>
  