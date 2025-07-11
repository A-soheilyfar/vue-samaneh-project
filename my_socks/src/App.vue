<template>
  <div>
    <button
      @click="toggleDark"
      class="fixed top-4 right-4 z-50 px-3 py-2 bg-gray-200 dark:bg-gray-700 text-black dark:text-white rounded-full shadow hover:scale-105 transition"
    >
      {{ isDark ? "☀️ روز" : "🌙 شب" }}
    </button>

    <router-view />
  </div>

  <homePage />
</template>

<script setup>
import homePage from "./views/homePage.vue";
import { ref, onMounted } from "vue";

const isDark = ref(false);

const toggleDark = () => {
  isDark.value = !isDark.value;
  document.documentElement.classList.toggle("dark", isDark.value);
  localStorage.theme = isDark.value ? "dark" : "light";
};

onMounted(() => {
  const stored = localStorage.theme;
  const prefers = window.matchMedia("(prefers-color-scheme: dark)").matches;
  isDark.value = stored === "dark" || (stored !== "light" && prefers);
  document.documentElement.classList.toggle("dark", isDark.value);
});
</script>
