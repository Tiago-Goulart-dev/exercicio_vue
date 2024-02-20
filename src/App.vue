<script setup>
  import { reactive } from 'vue';

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
    <header class="p-5 mb-4 mt-4 bg-light rounded-3">
      <h1>Calculadora Aritmética</h1>
    </header>
    <div class="row">
        <div class="col">
          <h4>Digite o Primeiro Número</h4>
        </div>
        <div class="col">
          <h4>Escolha a Operação</h4>
        </div>
        <div class="col">
          <h4>Digite o segundo número</h4>
        </div>
      </div>
    <form @submit.prevent>
      <div class="row">
        <div class="col">
          <input type="number" :value="numeros.num1" @change="evento => numeros.num1 = evento.target.value" placeholder="0" class="form-control text-center">
        </div>
        <div class="col">
          <select @change="evento => estado.opcao = evento.target.value" class="form-control text-center">
            <option value="adicao">Adição (+)</option>
            <option value="subtracao">Subtração (-)</option>
            <option value="multiplicacao">Multiplicação (*)</option>
            <option value="divisao">Divisão (/)</option>
          </select>
        </div>
        <div class="col">
          <input type="number" :value="numeros.num2" @change="evento => numeros.num2 = evento.target.value" placeholder="0" class="form-control text-center">
        </div>
      </div>
    </form>
    <div class="p-2 mb-2 mt-2 bg-light rounded-3">
        <div class="row" >
          <div class="col">
            <h3>Resultado</h3>
          </div>
        </div>
        <div class="row">
          <div class="col">
            <h3>{{ getOperacao() }} </h3>
          </div>
        </div>
      </div>
  </div>
</template>