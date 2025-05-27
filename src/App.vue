<script setup>
import { reactive } from 'vue';


const estado = reactive({
  filtro: 'adicao',
  primeiroNumero: 0,
  segundoNumero: 0,
  resultado: 0,
})

const imprimeResultado = () => {
  const { filtro } = estado

  switch (filtro) {
    case 'adicao':
      return estado.resultado = estado.primeiroNumero + estado.segundoNumero
    case 'subtracao':
      return estado.resultado = estado.primeiroNumero - estado.segundoNumero
    case 'multiplicacao':
      return estado.resultado = estado.primeiroNumero * estado.segundoNumero
    case 'divisao':
      return estado.resultado = estado.primeiroNumero / estado.segundoNumero
  }
}

</script>

<template>
  <div class="container">
    <header class="p-5 pb-2 mb-4 mt-4 bg-light rounded-3">
      <h1>Calculdora</h1>
      <p class="text-end">escolha abaixo a operação que deseja realizar <i class="bi bi-arrow-down"></i></p>
    </header>
    <form>
    <div class="row">
      <div class="col">
        <input type="number" placeholder="Digite o primeiro número" class="form-control" @keyup="evento => { estado.primeiroNumero = Number(evento.target.value); imprimeResultado()}">
      </div>
      <div class="col">
        <input type="number" placeholder="Digite o segundo número" class="form-control" @keyup="evento => { estado.segundoNumero = Number(evento.target.value); imprimeResultado()}">
      </div>
      <div class="col">
        <select @change="evento => { estado.filtro = evento.target.value; imprimeResultado() }" class="form-control">
          <option value="adicao">Adição</option>
          <option value="subtracao">Subtração</option>
          <option value="multiplicacao">Multiplicação</option>
          <option value="divisao">Divisão</option>
        </select>
      </div>
    </div>
  </form>
  <p class="resultado">
    {{ estado.resultado }}
  </p>
  </div>
  
</template>

<style scoped>

.resultado{
  font-size: 48px;
  font-weight: bold;
  margin: 10px;
}

</style>
