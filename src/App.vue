<script setup>

  //importacion del Paquete que me permite la reactividad en el DOM.
 import {ref, computed} from 'vue'

  //Aqui lo puedo definir como una constante porqu tiene mejor performance.
 const contador = ref(0);

  //Metodo de Incrementar
 const incrementar = () => contador.value++
  //Metodo de disminuir
 const disminuir = () => contador.value--
  //Metodo de Resetear
 const restaurar = () => contador.value = 0;

 // Cuando usamos un metodo computado siempre la funcion estrictamente
 // debe retornar ALGO
 // Para este caso particular estaria retornando el nombre de la clase
 const classCounter = computed(() => {
   if (contador.value === 0){
     return 'neutro';
   }
   if (contador.value>0){
     return 'positivo';
   }else{
     return 'negativo'
   }
 });

</script>

<template>
  <h1>Ejercicio de Reactividad de Vue</h1>
  <h2 v-bind:class="classCounter">Contador: {{contador}}</h2>
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