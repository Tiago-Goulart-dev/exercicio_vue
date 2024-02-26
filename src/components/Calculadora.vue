<script setup>
    const props = defineProps(['num1','num2','num1Temp', 'num2Temp','operacao']);
</script>

<template>
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
                <input type="number" :value="props.num1" @change="props.num1Temp" placeholder="0" class="form-control text-center">
            </div>
        <div class="col">
            <select @change="props.operacao" class="form-control text-center">
                <option value="adicao">Adição (+)</option>
                <option value="subtracao">Subtração (-)</option>
                <option value="multiplicacao">Multiplicação (*)</option>
                <option value="divisao">Divisão (/)</option>
            </select>
        </div>
        <div class="col">
            <input type="number" :value="props.num2" @change="props.num2Temp" placeholder="0" class="form-control text-center">
        </div>
        </div>
    </form>
</template>