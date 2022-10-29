<script setup>
import SourceData from "@/data.json";
const destinations = SourceData.destinations;
</script>
<template>
  <div class="home">
    <h2>{{ $route.params.id }}</h2>
    <h1>All Destinations</h1>
    <div class="destination-details">
      <router-link
        v-for="destination in destinations"
        :key="destination.id"
        :to="{
          name: 'destination.show',
          params: { id: destination.id, slug: destination.slug },
        }"
      >
        <h2>{{ destination.name }}</h2>
        <img :src="`images/${destination.image}`" :alt="destination.name" />
        <p>{{ destination.title }}</p>
      </router-link>
    </div>
  </div>
</template>
