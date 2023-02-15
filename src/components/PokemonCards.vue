<script setup>
// import {ref, watch} from "vue"
import axios from "axios"

// const pokemons = ref(null)
// const page = ref(0)

const response = await axios.get("https://pokeapi.co/api/v2/pokemon/?limit=10")

console.log(response)
</script>

<template>
	<div>
        <h1>Pokemon Cards</h1>
        {{ response.data.results.length }}
    </div>
</template>