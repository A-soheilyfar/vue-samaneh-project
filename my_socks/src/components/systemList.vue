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

const systems = [
  {
    id: 1,
    title: "سامانه آنلاین امداد",
    image: "https://source.unsplash.com/featured/400x300/?emergency",
  },
  {
    id: 2,
    title: "سامانه شهرسازی درآمد",
    image: "https://source.unsplash.com/featured/400x300/?city,planning",
  },
  {
    id: 3,
    title: "سامانه خدمات شهری",
    image: "https://source.unsplash.com/featured/400x300/?municipality",
  },
];

function selectSystem(id) {
  alert(`شما روی سامانه ${id} کلیک کردید`);
}
</script>
