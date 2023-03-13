<script setup>
import PokemonCards from "./components/PokemonCardsSuspense.vue";
import PracticeSlot from "./components/PracticeSlot.vue";
import RickMortyCards from "./components/RickMortyCards.vue";
import Hero from "./components/Hero.vue";
import { ref } from "vue";

const isPokemon = ref(true);
</script>

<template>
  <main>
    <Hero :isPokemon="isPokemon" @selectShow="isPokemon = !isPokemon" />

    <KeepAlive>
      <Component :is="isPokemon ? PokemonCards : RickMortyCards" />
    </KeepAlive>
    <!-- <PracticeSlot>
      <div>
        <h1>Hello</h1>
      </div> -->
    <!-- spesifik slot dengan tag template id sesuai dengan name di slot child element-->
    <!-- <template #header>
        <h1 style="font-weight: bolder; font-size: 20px">Header dari slot</h1>
      </template>
    </PracticeSlot> -->
  </main>
</template>

<style scoped></style>
