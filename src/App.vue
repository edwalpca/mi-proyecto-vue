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
 const restaurar = ()=> {
   contador.value = 0;
   listaNumeros.value
 }

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

 // Arreglo de numeros seleccionados por el usuario
  const listaNumeros = ref([]);


  const bloqueo = computed(()=>{
    const numSearch =listaNumeros.value.find((num)=> num === contador.value);
    return numSearch ? true : false;

  });

  const existe = () => {
    for(var i = 0; i < listaNumeros.value.length; i++){
      if( listaNumeros.value[i] == contador.value){
        return true
      }
    }
    return false
  };


  //Metodo que Agrega numeros a mi lista
  const agregar = () => {

    if (!existe(contador.value)){
      //Agrego a mi Lista un nuevo valor
      listaNumeros.value.push(contador.value);
    }


    console.log(listaNumeros);

  }

</script>

<template>
  <h1>Ejercicio de Reactividad de Vue</h1>
  <h2 v-bind:class="classCounter">Contador: {{contador}}</h2>
  <div class="container text-center mt">
    <div class="btn-group">
      <button class="btn btn-success" @click="incrementar">Aumentar Contador</button>
      <button class="btn btn-danger" @click="disminuir">Disminuir Contador</button>
      <button class="btn btn-secondary" @click="restaurar">Resetar Contador</button>
      <button class="btn btn-primary"  @click="agregar" :disabled="bloqueo">Agregar [+]</button>
    </div>
  </div>

  <h3>{{listaNumeros}}</h3>
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