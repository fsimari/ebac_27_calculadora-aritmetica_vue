<template>
  <div class="container mt-5">
    <h1>Calculadora Aritmética</h1>
    <div class="row mt-4">
      <div class="col-md-3">
        <input v-model.number="num1" type="number" class="form-control" placeholder="Número 1" />
      </div>
      <div class="col-md-3">
        <select v-model="operacao" class="form-control">
          <option value="adicao">+</option>
          <option value="subtratracao">-</option>
          <option value="multiplicacao">*</option>
          <option value="divicao">/</option>
        </select>
      </div>
      <div class="col-md-3">
        <input v-model.number="num2" type="number" class="form-control" placeholder="Número 2" />
      </div>
      <div class="col-md-3">
        <button @click="calcular" class="btn btn-primary">Calcular</button>
      </div>
    </div>
    <div class="row mt-4">
      <div class="col-md-9">
        <h2 class="resultado">Resultado: {{ resultado }}</h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operacao: 'adicao',
      resultado: null
    };
  },
  methods: {
    calcular() {
      switch (this.operacao) {
        case 'adicao':
          this.resultado = this.num1 + this.num2;
          break;
        case 'subtratracao':
          this.resultado = this.num1 - this.num2;
          break;
        case 'multiplicacao':
          this.resultado = this.num1 * this.num2;
          break;
        case 'divicao':
          this.resultado = this.num2 !== 0 ? this.num1 / this.num2 : 'Erro: Divisão por zero';
          break;
        default:
          this.resultado = 0;
      }
    }
  }
};
</script>

<style scoped>
.btn-primary {
  border: 2px solid blue;
}

.resultado {
  border: 2px solid green;
  background-color: lightblue;
  padding: 10px;
}
</style>
