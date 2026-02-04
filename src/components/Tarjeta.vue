<script setup>

defineProps({
  nombre:String,
  tipo:String,
  edad:Number,
  vacunado:Boolean,
  foto:String,
  caracteristicas:Array
})

</script>

<template>

  <article>
   <!--  ==== interpolaciones ==== -->
    <h2>{{ nombre }}</h2>
    <p>{{ tipo }}</p>
    <p>{{ edad }} años</p>

    <!-- ==== renderización condicional si está vacunado o no ==== -->
    <p>
      <span v-if="vacunado">Vacunado ✔</span>
      <span v-else>No vacunado ❌</span>
    </p>

   <!--  ==== atributos dinámicos ==== -->
    <img :src="foto" :alt="nombre">

    <!-- ==== renderizado de listas ==== -->
    <p class="lista">Características</p>
    <ul v-for="(caracteristica, index) in caracteristicas" :key="index">
      <li>{{caracteristica}}</li>
    </ul>
  </article>
 
</template>

<style>

article{
  display: flex;
  flex-direction: column;
  gap: 1em;
  padding: 1em;
  border: solid 2px #424242;
  border-radius: 5px;
  flex-basis: 200px;
}

h2{
  align-self: center;
}
img{
  order: -1;
  width: 50%;
  aspect-ratio: 1/1;
  object-fit: cover;
  border-radius: 50%;
  align-self: center;
}
.lista{
  text-decoration: underline;
  margin-block: .5em;
}
ul{
  list-style-type: none;
  padding-inline-start: 1em;
}
ul>li::marker{
  content: "🐾 ";
  
}


</style>
