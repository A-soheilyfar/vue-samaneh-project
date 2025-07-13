<template>
  <div>
    <button
      @click="toggleDark"
      class="fixed top-4 right-4 z-50 px-3 py-2 bg-gray-700 dark:bg-gray-200 text-white dark:text-black rounded-full hover:shadow-yellow-400 dark:hover:shadow-gray-700 shadow-lg hover:scale-105 transition border-none outline-none"
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
  document.body.classList.toggle("dark");
  localStorage.theme = isDark.value ? "dark" : "light";
};

onMounted(() => {
  const stored = localStorage.theme;
  const prefers = window.matchMedia("(prefers-color-scheme: dark)").matches;
  isDark.value = stored === "dark" || (stored !== "light" && prefers);
  document.documentElement.classList.toggle("dark", isDark.value);
});
</script>
