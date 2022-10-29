<script setup>
import { computed } from "vue";
import { useRoute } from "vue-router";
import SourceData from "@/data.json";
const route = useRoute();
const destination = computed(() => {
  return SourceData.destinations.find(
    (destination) => destination.id === Number(route.params.id)
  );
});
</script>
<template>
  <section class="destination">
    <h1>{{ destination.name }}</h1>
    <div class="destination-details">
      <img :src="`/images/${destination.image}`" :alt="destination.name" />
      <p>{{ destination.description }}</p>
    </div>
  </section>
  <section class="experiances">
    <h2>Top Experiances in {{ destination.name }}</h2>
    <div
      class="card"
      v-for="experiance in destination.experiances"
      :key="experiance.slug"
    >
      <span class="card_text"> {{ experience.name }} Hey </span>
    </div>
  </section>
</template>
