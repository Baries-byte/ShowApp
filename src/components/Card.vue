<script setup>
import { defineProps } from "vue";

const { name, image } = defineProps(["name", "image"]);
</script>

<template>
  <n-card>
    <template #cover>
      <img :src="image" />
    </template>
    <h3>{{ name }}</h3>
    <slot></slot>
  </n-card>
</template>
<style scoped>
.n-card {
  width: 200px;
  height: 300px;
  margin: 10px 20px;
}
.n-card img {
  height: 250px;
}

p {
  font-size: 10px;
}

.jobs {
  display: flex;
  flex-wrap: wrap;
}
</style>
