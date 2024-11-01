<template>
  <div id="App" class="container">
    <div class="form-group columns">
      <input 
        class="form-input column col-1" 
        type="number" 
        v-model.number="value1" 
        placeholder="Insira número" 
      />
      <select 
        class="form-select column col-1" 
        v-model="operator"
      >
        <option disabled value="">Escolha um operador</option>
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input 
        class="form-input column col-1" 
        type="number" 
        v-model.number="value2" 
        placeholder="Insira número" 
      />
    </div>
    <p>Resultado: {{ result }}</p>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      value1: 0,
      value2: 0,
      operator: ""
    };
  },
  computed: {
    result() {
      if (this.operator === "+") return this.value1 + this.value2;
      if (this.operator === "-") return this.value1 - this.value2;
      if (this.operator === "*") return this.value1 * this.value2;
      if (this.operator === "/") {
        return this.value2 !== 0 ? this.value1 / this.value2 : "Erro: divisão por zero";
      }
      return "Escolha um operador";
    }
  }
};
</script>

<style>
  .container {
    display: flex;
    flex-direction: column;
  }
</style>
