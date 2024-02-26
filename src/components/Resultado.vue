<script setup>
    const props = defineProps(['result']);
</script>

<template>
    <div class="p-2 mb-2 mt-2 bg-light rounded-3">
        <div class="row" >
            <div class="col">
                <h3>Resultado</h3>
            </div>
        </div>
        <div class="row">
            <div class="col">
                <h3>{{ props.result }} </h3>
            </div>
        </div>
    </div>
</template>