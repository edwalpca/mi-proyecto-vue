<script setup>

  //importacion del Paquete que me permite la reactividad en el DOM.
  import {ref} from 'vue'

  //Aqui lo puedo definir como una constante porqu tiene mejor performance.
 const contador = ref(0);

  //Metodo de Incrementar
 const incrementar = () => contador.value++
  //Metodo de disminuir
 const disminuir = () => contador.value--
  //Metodo de Resetear
 const restaurar = () => contador.value = 0;

 //Parte de La Solucion #1
  const textoRojo  = 'color: red';
  const textoVerde = 'color: green';
  const textogris = 'color: grey';

</script>

<template>

  <h1>Ejercicio de Reactividad de Vue</h1>
  <template v-if="(contador > 0)">
    <h2 v-bind:style="textoVerde"> Contador: {{contador}}</h2>
  </template>
  <template v-else-if="(contador == 0)">
    <h2 :style="textogris"> Contador: {{contador}}</h2>
  </template>
  <template v-else>
    <h2 v-bind:style="textoRojo"> Contador: {{contador}}</h2>
  </template>

  <h2 v-bind:class="( contador > 0 ) ? 'positivo': ( contador == 0 ) ? 'neutro': 'negativo' ">Contador: {{contador}}</h2>

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

.negativo{
  color: red;
}
.positivo{
  color: green;
}
.neutro{
  color: grey;

}

</style>