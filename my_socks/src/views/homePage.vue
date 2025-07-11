<template>
  <div class="min-h-screen bg-gray-100 flex flex-col items-center justify-start p-6 space-y-8">
    <!-- فرم ورود -->
    <LoginForm />

    <!-- لیست کارت‌ها -->
    <SystemList />
  </div>
</template>

<script setup>
import LoginForm from "../components/heroForm.vue";
import SystemList from "../components/systemList.vue";
</script>
