<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';


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
    <Cabecalho />
    <Formulario
      :edita-primeiro-numero="evento => { estado.primeiroNumero = Number(evento.target.value); imprimeResultado() }"
      :edita-segundo-numero="evento => { estado.segundoNumero = Number(evento.target.value); imprimeResultado() }"
      :edita-filtro="evento => { estado.filtro = evento.target.value; imprimeResultado() }"
    />
    <Resultado
      :resultado="estado.resultado"
    />
  </div>
  
</template>

<style scoped>

.resultado{
  font-size: 48px;
  font-weight: bold;
  margin: 10px;
}

</style>
