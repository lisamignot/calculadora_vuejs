<script setup>
const props = defineProps(['primeiroCampo', 'segundoCampo', 'atualizaprimeiroCampo', 'atualizasegundoCampo', 'operacao', 'defineOperacao'])
</script>

<template>
    <div class="row px-5">
        <div class="col-md-6 d-flex flex-column align-items-end">
        <input :value="props.primeiroCampo" @change="props.atualizaprimeiroCampo" required type="number" class="form-control mb-3" placeholder="Insira o 1º número">
        <input :value="props.segundoCampo" @change="props.atualizasegundoCampo" required type="number" class="form-control" placeholder="Insira o 2º número">
    </div>
    
    <div class="col-md-6 d-flex justify-content-center align-items-center">
        <select :value="props.operacao" @change="props.defineOperacao" class="form-control text-center mt-3 mb-3 w-75 select-style">
            <option disable value="operacao">Defina a operação ↓</option>
            <option class="operadorValido" value="somar">+ (somar)</option>
            <option class="operadorValido" value="subtrair">- (subtrair)</option>
            <option class="operadorValido" value="dividir">/ (dividir)</option>
            <option class="operadorValido" value="multiplicar">* (multiplicar)</option>
        </select>
        </div>
    </div>
</template>

<style scoped>
input {
    border: 2px solid transparent;
    box-shadow: 3px 3px 10px #0000001f;

    &:hover {
        cursor: pointer;
        box-shadow: 5px 5px 10px #00000063;
    }
    &:focus {
        box-shadow: none;
        border: 2px solid #3a3939;
    }
}
.select-style {
    border: 2px solid #f347474d;
    box-shadow: 3px 3px 10px #0000001f;

    &:hover {
        cursor: pointer;
        font-weight: 500;
        box-shadow: 5px 5px 10px #f0141488;
    }
    &:focus {
        box-shadow: none;
        border: 2px solid transparent;
    }
}
</style>