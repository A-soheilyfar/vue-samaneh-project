<template>
  <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 w-full max-w-6xl">
    <systemCard
      v-for="system in systems"
      :key="system.id"
      :title="system.title"
      :image="system.image"
      @click="selectSystem(system.id)"
    />
  </div>
</template>

<script setup>
import systemCard from "./systemCard.vue";

const systems = ref([
  {
    id: 1,
    title: "سامانه آنلاین امداد",
    query: "emergency",
    image: "",
  },
  {
    id: 2,
    title: "سامانه شهرسازی درآمد",
    query: "urban planning",
    image: "",
  },
  {
    id: 3,
    title: "سامانه خدمات شهری",
    query: "municipality service",
    image: "",
  },
]);

import { ref, onMounted } from "vue";

const fetchImage = async (query) => {
  const apiKey = "51279325-df4cf9562eae1a047cbaae140";
  const url = `https://pixabay.com/api/?key=${apiKey}&q=${encodeURIComponent(
    query
  )}&image_type=photo`;
  const res = await fetch(url);
  const data = await res.json();
  return data.hits?.[0]?.webformatURL || "";
};

//
onMounted(async () => {
  for (let system of systems.value) {
    const image = await fetchImage(system.query);
    system.image = image;
  }
});

function selectSystem(id) {
  alert(`شما روی سامانه ${id} کلیک کردید`);
}
</script>
