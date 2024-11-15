<script setup>
const props = defineProps(['resultado'])
</script>

<template>
    <p class="mt-5 pb-5 px-5 text-center">O resultado da sua conta é:
        <span><b>{{ props.resultado }}</b></span>
    </p>
</template>

<style scope>
    p {
        color: black;
        letter-spacing: 1px
    }
    span {
        letter-spacing: 0;
    }
</style>