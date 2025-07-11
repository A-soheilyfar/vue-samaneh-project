<template>
  <!-- Title of Form -->
  <div class="bg-white shadow-lg rounded-xl p-6 w-full max-w-sm">
    <h2 class="text-2xl font-semibold text-center text-gray-700 mb-6">ورود به سامانه</h2>

    <!-- Form -->

    <form action="#" @submit.prevent="handleLogin">
      <!-- user -->
      <div class="mb-4">
        <label for="username" class="block text-sm text-gray-600 mb-1">نام کاربری</label>
        <input
          id="username"
          v-model="username"
          type="text"
          class="w-full px-4 py-2 border border-light-secondary rounded-lg focus:outline-none focus:ring-2 focus:ring-light-primary"
          placeholder="مثال : admin"
        />
        <!-- using v-model to connect to ref variable in Script section -->
      </div>
      <!-- pass -->
      <div class="mb-4">
        <label class="block text-sm text-gray-600 mb-1" for="password">رمز عبور</label>
        <input
          type="password"
          v-model="password"
          class="w-full px-4 py-2 border border-light-secondary rounded-lg focus:outline-none focus:ring-2 focus:ring-light-primary"
          placeholder="******"
        />
      </div>

      <button
        type="submit"
        class="w-full bg-light-secondary text-white py-2 rounded-lg hover:bg-light-primary"
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
    alert("لطفا فیلد های خالی را پر نمائید");
    return;
  }
  alert("شما وارد شدید");
}
</script>

<style scoped></style>
