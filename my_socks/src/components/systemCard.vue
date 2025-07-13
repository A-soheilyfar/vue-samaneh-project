<template>
  <div
    @click="handleClick"
    class="transition duration-400 cursor-pointer bg-gradient-to-br from-light-white to-white dark:from-purple-950 dark:to-blue-950 rounded-2xl shadow-lg hover:shadow-xl overflow-hidden transform hover:scale-105"
  >
    <img :src="image" alt="system image" class="w-full h-48 object-cover" />
    <!-- w-24 h-24 object-contain mb-4 -->
    <div class="p-4">
      <h3 class="text-lg font-bold text-gray-700 dark:text-indigo-50 text-center">
        {{ title }}
      </h3>
    </div>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  image: String,
});

const emit = defineEmits(["click"]);

function handleClick() {
  emit("click");
}
</script>
