<script setup>
  import { reactive } from 'vue';
  import Calculadora from './components/Calculadora.vue';
  import Resultado from './components/Resultado.vue';

//estado reativo
  const estado = reactive({
    primeiroCampo: null,
    segundoCampo: null,
    operacao: 'operacao',
  })

  //escolher e realizar operacão aritmética
  const mostraResultado = () => {
    const { primeiroCampo, segundoCampo, operacao} = estado;

    const numero1 = Number(primeiroCampo);
    const numero2 = Number(segundoCampo);

    switch (operacao) {
      case "somar":
        return `a soma dos valores é ${numero1 + numero2}`;
      case "subtrair":
        return `a subtração dos valores é ${numero1 - numero2}`;
      case "dividir":
        if (numero2 === 0) {
          return 'Insira um número válido no segundo campo.';
        } else {
          const resultadoDaDivisao = numero1 / numero2;
          if (!Number.isInteger(resultadoDaDivisao)) {
            const valorInteiro = Math.floor(resultadoDaDivisao);
            const valorResidual = numero1 % numero2;
              return `a divisão dos valores é ${valorInteiro}, com resto ${valorResidual}`
          } else {
            return `a divisão dos valores é ${numero1 / numero2}`;
          }    
        }
      case "multiplicar":
        return `a multiplicação dos valores é ${numero1 * numero2}`;
      default:
        return '';  
    }
    estado.operacao = 'operacao';
    return resultado;
  }
</script>

<template>
  <div class="container mt-5 mb-5">
    <header class="pt-5 px-5 text-center">
      <h1 class="pb-3">Calculadora</h1>
      <p class="lead text-start">Faça seu cálculo:</p>
    </header>

<!-- componentes -->
    <Calculadora 
    :primeiroCampo="estado.primeiroCampo"
    :segundoCampo="estado.segundoCampo"
    :operacao="estado.operacao"
    :atualizaprimeiroCampo="(e) => estado.primeiroCampo = e.target.value"
    :atualizasegundoCampo="(e) => estado.segundoCampo = e.target.value"
    :defineOperacao="(e) => estado.operacao = e.target.value"/>

    <Resultado :resultado="mostraResultado()"/>
  </div>
</template>

<style scoped>
.container {
  box-shadow: border-box;
  width: 700px;
  background-color: #ff000071;
  color: #3a3939;
  border-radius: 10px;
}
</style>
