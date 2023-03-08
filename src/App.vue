<script setup>
import { reactive } from 'vue';
import Header from './components/header.vue';
import Corpo from './components/Corpo.vue';

const estado = reactive({
  operacao: 'Somar',
  numero1: 0,
  numero2: 0,
  resultado: 0,
});

const somar = () => estado.resultado = Number(estado.numero1) + Number(estado.numero2);
const subtrair = () => estado.resultado = Number(estado.numero1) - Number(estado.numero2);
const multiplicar = () => estado.resultado = Number(estado.numero1) * Number(estado.numero2);
const dividir = () => estado.resultado = Number(estado.numero1) / Number(estado.numero2);

const filtrarOperacao = () => {
  switch (estado.operacao) {
    case 'Somar':
      return somar();
    case 'Subtrair':
      return subtrair();
    case 'Multiplicar':
      return multiplicar();
    case 'Dividir':
      return dividir();
    default: '';
  }
}

</script>

<template>
  <div class="container">
    <Header />
    <Corpo 
    :trocar-operacao="evento => estado.operacao = evento.target.value" 
      :operacao="filtrarOperacao()"
      :numero1="evento => estado.numero1 = evento.target.value"
      :numero2="evento => estado.numero2 = evento.target.value" />
  </div>
</template>
