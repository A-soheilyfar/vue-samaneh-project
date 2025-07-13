<template>
  <!-- Title of Form -->
  <div
    class="transition-colors duration-400 bg-gradient-to-br from-light-white to-white dark:from-purple-950 dark:to-blue-950 shadow-lg rounded-xl p-6 w-full max-w-sm"
  >
    <h2 class="text-2xl font-semibold text-center text-gray-700 dark:text-indigo-50 mb-6">
      ورود به سامانه
    </h2>

    <!-- Form -->

    <form action="#" @submit.prevent="handleLogin">
      <!-- user -->
      <div class="mb-4">
        <label
          for="username"
          class="block text-sm text-gray-600 dark:text-indigo-50 mb-1 text-right"
          >نام کاربری</label
        >
        <input
          id="username"
          v-model="username"
          type="text"
          class="w-full px-4 py-2 border border-light-primary dark:text-indigo-50 rounded-lg focus:outline-none focus:ring-2 focus:ring-light-third"
          placeholder="admin"
        />
        <!-- using v-model to connect to ref variable in Script section -->
      </div>
      <!-- pass -->
      <div class="mb-4 text-right">
        <label class="block text-sm text-gray-600 dark:text-indigo-50 mb-1" for="password"
          >رمز عبور</label
        >
        <input
          type="password"
          v-model="password"
          class="w-full px-4 py-2 border dark:text-indigo-50 border-light-primary rounded-lg focus:outline-none focus:ring-2 focus:ring-light-third"
          placeholder="******"
        />
      </div>

      <button
        type="submit"
        class="font-semibold w-full bg-light-primary text-light-white py-2 rounded-lg hover:bg-light-third"
      >
        ورود
      </button>
    </form>
  </div>
</template>

<script setup>
import { ref } from "vue";
const username = ref("");
const password = ref("");
function handleLogin() {
  if (!username.value || !password.value) {
    alert("لطفا فیلد های خالی را پر نمائید⚠️");
    return;
  }
  alert("شما وارد شدید ✅");
}
</script>

<style scoped></style>
