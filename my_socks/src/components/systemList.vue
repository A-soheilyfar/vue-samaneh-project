<template>
  <div class="grid grid-cols-1 sm:grid-cols-2 gap-6 w-full max-w-3x1">
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
    image: "https://placehold.co/100x100?text=Emdad",
  },
  {
    id: 2,
    title: "سامانه شهرسازی درآمد",
    image: "https://placehold.co/100x100?text=Daramad",
  },
];

function selectSystem(id) {
  alert(`شما روی سامانه ${id} کلیک کردید`);
}
</script>
