<script setup>
</script>

<template>
  <div class="container mt-5 mb-5">
    <header class="p-5 text-center">
      <h1 class="pb-3">Calculadora</h1>
      <p class="lead text-start">Faça seu cálculo:</p>

      <div class="row">
        <div class="col-md-8 d-flex flex-column align-items-end">
          <input type="number" class="form-control mb-3" placeholder="1º número">
          <input type="number" class="form-control" placeholder="2º número">
        </div>
        <div class="col-md-4 d-flex justify-content-center align-items-center">
          <select class="form-control text-center w-50">
            <option value="somar">+</option>
            <option value="subtrair">-</option>
            <option value="dividir">/</option>
            <option value="multiplicar">*</option>
          </select>
        </div>
      </div>
      <p class="mt-5">O resultado da sua conta é: 
        <span><b>1223</b></span>
      </p>
    </header>
  </div>
</template>

<style scoped>
.container {
  width: 400px;
  background-color: rgba(255, 0, 0, 0.445);
  color: rgb(43, 40, 40);
  border-radius: 10px;
  color: rgb(58, 58, 58);
}
</style>
