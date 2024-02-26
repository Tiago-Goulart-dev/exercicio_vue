<script setup>
  import { reactive } from 'vue';
  import Cabecalho from './components/Cabecalho.vue';
  import Calculadora from './components/Calculadora.vue';
  import Resultado from './components/Resultado.vue';

  const estado = reactive({
    opcao: 'adicao',
  })

  const numeros = reactive({
    num1: 0,
    num2: 0,
  })

  const adicao = () =>{
    const resultado = +numeros.num1 + +numeros.num2;
    return resultado;
  }

  const subtracao = () =>{
    const resultado = numeros.num1 - numeros.num2;
    return resultado;
  }

  const multiplicacao = () =>{
    const resultado = numeros.num1 * numeros.num2;
    return resultado;
  }

  const divisao = () =>{
    const resultado = numeros.num1 / numeros.num2;
    return resultado;
  }

  const getOperacao = () =>{
    const {opcao} = estado;

    switch(opcao){
      case 'adicao':
      return adicao();
      case 'subtracao':
      return subtracao();
      case 'multiplicacao':
      return multiplicacao();
      case 'divisao':
      return divisao();
    }
  }
</script>

<template>
  <div class="container text-center">
    <Cabecalho/>
    <Calculadora :num1="numeros.num1" :num1-temp="evento => numeros.num1 = evento.target.value" :operacao="evento => estado.opcao = evento.target.value" :num2="numeros.num2" :num2-temp="evento => numeros.num2 = evento.target.value"/>
    <Resultado :result="getOperacao()"/>
  </div>
</template>