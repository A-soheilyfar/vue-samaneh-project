<template>
  <div
    @click="handleClick"
    class="cursor-pointer bg-gradient-to-br from-light-white to-white rounded-2xl shadow-lg hover:shadow-xl transition-all duration-300 overflow-hidden transform hover:scale-105"
  >
    <img :src="image" alt="system image" class="w-full h-48 object-cover" />
    <!-- w-24 h-24 object-contain mb-4 -->
    <div class="p-4">
      <h3 class="text-lg font-bold text-gray-700 text-center">
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
