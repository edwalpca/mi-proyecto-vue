<script setup>

  const nombreUsuario = 'Mauricio A';

  const styleColorP = 'color: #D8eAA3';

  const aColores = ["Azul","Rojo","Blanco"]

  const activo = false;

  //Un Arreglo Simple
  const superHeroes = ["SuperMan","Hombre Arana","Mujer Maravilla","Venom","Hulk","Flash"];

  const productos = [
    {
      id:1,
      name:'Manzana',
      price:'$1.00',
      descripcion:'Una Manzada',
      stock:3
    },
    {
      id:2,
      name:'Pera',
      price:'$3.00',
      descripcion:'Una Pera',
      stock:0

    },
    {
      id:3,
      name:'Naranja',
      price:'$3.00',
      descripcion:'Una Naranja',
      stock:13

    },
    {
      id:4,
      name:'Papaya',
      price:'$3.50',
      descripcion:'Una papaya',
      stock:6
    }
  ];

  const objetoPersona = {
    nombre:'Mauricio',
    Apellidos:'Alpizar',
    Edad:'55',
    identificacion:'110660786',
  }

</script>

<template>
  <h1 > Hola {{nombreUsuario.toUpperCase()}}</h1>
  <h3>Mi Proyecto de Vue 3</h3>
  <p  v-bind:style="styleColorP" > Texto Pintado: Ittt is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. </p>
  <p>&nbsp;</p>
  <h3> Colores del arreglo: {{aColores}}</h3>

  <p>&nbsp;</p>
  <h2> Validacion Ternaria:  {{activo ? 'Estoy Online' : 'Estoy Offline' }}</h2>
  <p>&nbsp;</p>
  <h2>Recorrido de un arreglo simple de String</h2>
  <ul>
    <li v-for="(heroe,index) in superHeroes" :key="index">
      {{heroe}}
    </li>
  </ul>
  <hr/>
  <p>&nbsp;</p>
  <h2>Recorrido de un Arreglo conjunto de Objetos</h2>
  <ul>
    <li v-for="(producto,index) of productos" :key="producto.id">
      ID:{{producto.id}} - Nombre: {{producto.name}} Precio:  {{producto.price}} - Stock: {{producto.stock}}
    </li>
  </ul>

  <p>&nbsp;</p>
  <h2>Recorrido de un Objeto</h2>
  <ul>
    <li v-for="(value,propiedad,index) in objetoPersona" :key="index">
      {{index}} -  {{propiedad}} : {{value}}
    </li>
  </ul>

  <p>&nbsp;</p>
  <h2>Recorrido de un Arreglo con la directiva [v-if] Condicional</h2>
  <ul>
    <template v-for="(producto,index) of productos" :key="producto.id">
      <li v-if=" ( producto.stock > 0 ) ">
        ID:{{producto.id}} - Nombre: {{producto.name}} Precio:  {{producto.price}} - Stock: {{producto.stock}}
      </li>
    </template>
  </ul>
</template>




<style>
h1{
  color:brown;
}
</style>