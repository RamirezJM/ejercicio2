<script setup>
import { ref } from "vue"
import Tarjeta from "./components/Tarjeta.vue";

/* En lugar del objeto data de la Options API, uso la
forma similar en la Composition API, ref() */

const mascotas = ref([
  {
    id: 1,
    nombre: "Firulais",
    tipo: "Perro",
    edad: 4,
    vacunado: true,
    foto: "https://placedog.net/500/350?id=8",
    caracteristicas: ["Juguetón", "Cariñoso", "Sociable"]
  },
  {
    id: 2,
    nombre: "Michi",
    tipo: "Gato",
    edad: 2,
    vacunado: false,
    foto: "https://placecats.com/500/350",
    caracteristicas: ["Curioso", "Dormilón", "Independiente"]
  },
  {
    id: 3,
    nombre: "Rocky",
    tipo: "Perro",
    edad: 7,
    vacunado: true,
    foto: "https://placedog.net/500/350?id=5",
    caracteristicas: ["Tranquilo", "Leal"]
  }
])
</script>

<template>

  <h1>Elige tu mascota ideal</h1>
  <section class="mascotas">
    <Tarjeta v-for="({ id, nombre, tipo, edad, vacunado, foto, caracteristicas }) in mascotas" :key="id" 
    :nombre="nombre"
    :tipo="tipo" 
    :edad="edad" 
    :vacunado="vacunado" 
    :foto="foto" 
    :caracteristicas="caracteristicas" />
  </section>
</template>

<style>
h1{
  text-align: center;
  margin: 1em auto;
}

.mascotas{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1em;
  padding: 3em;

}
</style>
