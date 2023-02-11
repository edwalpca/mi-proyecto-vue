<script setup>

  // configuracion de Estilos.
  const styleColorP = 'color: #558800';
  const styleH2 = 'color: blue; font-family: "Roboto", Helvetica, Arial; font-weight: 600';

  const nombreUsuario = 'Mauricio A';

  //Arreglo de String.
  const aColores = ["Azul","Rojo","Blanco"]

  //Variable Booleana
  const activo = false;

  //Un Arreglo Simple de SuperHeroes
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

  <h1> Hola {{nombreUsuario.toUpperCase()}}</h1>
  <h2>Mi Proyecto de Vue 3</h2>
  <p v-bind:style="styleColorP" > Texto Pintado: Ittt is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. </p>
  <p>&nbsp;</p>
  <h3> Colores del arreglo: {{aColores}}</h3>



  <p>&nbsp;</p>
  <h2 :style="styleH2"> Validacion Ternaria:  {{activo ? 'Estoy Online' : 'Estoy Offline' }}</h2>
  <p>&nbsp;</p>
  <h2 :style="styleH2">Recorrido de un arreglo simple de String</h2>
  <ul>
    <li v-for="(heroe,index) in superHeroes" :key="index">
      {{heroe}}
    </li>
  </ul>


  <p>&nbsp;</p>
  <h2 :style="styleH2">Recorrido de un Arreglo conjunto de Objetos</h2>
  <ul>
    <li v-for="(producto,index) of productos" :key="producto.id">
      ID:{{producto.id}} - Nombre: {{producto.name}} Precio:  {{producto.price}} - Stock: {{producto.stock}}
    </li>
  </ul>

  <p>&nbsp;</p>
  <h2 :style="styleH2">Recorrido de un Objeto</h2>
  <ul>
    <li v-for="(value,propiedad,index) in objetoPersona" :key="index">
      {{index}} -  {{propiedad}} : {{value}}
    </li>
  </ul>

  <p>&nbsp;</p>
  <h2 :style="styleH2">Recorrido de un Arreglo con la directiva [v-if] Condicional</h2>
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
  font-family: "Roboto";
  color: brown;
  font-weight: 800;
  font-style: normal;
  font-display: auto;
  unicode-range: U+000-5FF;
}
</style>