<template>
  <div
    class="transition-colors duration-400 min-h-screen bg-light-white dark:bg-gray-800 flex flex-col items-center justify-start p-6 py-12 space-y-8"
  >
    <!-- فرم ورود -->
    <heroForm />

    <!-- لیست کارت‌ها -->
    <systemList />
    <!-- فوتر -->
    <footerMain />
  </div>
</template>

<script setup>
import heroForm from "../components/heroForm.vue";
import systemList from "../components/systemList.vue";
import footerMain from "../components/footerMain.vue";
</script>
