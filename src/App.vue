<script setup>

  //importacion del Paquete que me permite la reactividad en el DOM.
  import {ref} from 'vue'

  //Aqui lo puedo definir como una constante porqu tiene mejor performance.
 const contador = ref(0);


  //Metodo de Incrementar
 const incrementar = () => {
   contador.value++;
   console.log(contador);
 };

  //Metodo de disminuir
 const disminuir = () => {
   contador.value--;
   console.log(contador);
 }

  //Metodo de Resetear
 const restaurar = () => {
   contador.value = 0;
   console.log(contador);
 }
</script>



<template>
  <h1>Ejercicio de Reactividad de vue</h1>
  <h2> Contador: {{contador}}</h2>

  <div>
  <button @click="incrementar">Aumentar Contador</button>
  <button @click="disminuir">Disminuir Contador</button>
  <button @click="restaurar">Resetar Contador</button>
  </div>
</template>


<style>
button{
  margin: 10px;
}
</style>