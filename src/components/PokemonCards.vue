<script setup>
import { ref, watch } from "vue";
import axios from "axios";

import Card from "./Card.vue";

const pokemons = ref(null);
const page = ref(0);

const response = await axios.get("https://pokeapi.co/api/v2/pokemon/?limit=8");

pokemons.value = response.data.results;

watch(page, async () => {
  const res = await axios.get(
    `https://pokeapi.co/api/v2/pokemon/?limit=8&offset=${page.value * 8}`
  );
  pokemons.value = res.data.results;
  console.log(pokemons.value);
});
</script>

<template>
  <div class="container">
    <div class="cards">
      <Card
        v-for="pokemon in pokemons"
        :image="pokemon.image"
        :key="pokemon.id"
        :name="pokemon.name"
      />
    </div>
    <div class="button-container">
      <button @click="page--" class="button">&lt;</button>
      <button @click="page++" class="button">&gt;</button>
    </div>
  </div>
</template>

<style scoped>
.container {
  background-color: rgb(27, 26, 26);
  padding: 30px;
}
.cards {
  max-width: 1000px;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  height: 700px;
}
.cards h3 {
  font-weight: bold;
}
.cards p {
  font-size: 10px;
}
.jobs {
  display: flex;
  flex-wrap: wrap;
}
.button-container {
  display: flex;
  justify-content: center;
  padding-top: 30px;
}
.button-container button {
  border: none;
  width: 50px;
  height: 50px;
  border-radius: 100%;
  margin: 0 5px;
  font-weight: bolder;
  cursor: pointer;
}
.spinner {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
