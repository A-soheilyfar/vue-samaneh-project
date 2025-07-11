<template>
  <div
    @click="handleClick"
    class="cursor-pointer bg-white rounded-xl shadow-md hover:shadow-lg transition-all duration-300 p-4 flex flex-col items-center justify-center text-center"
  >
    <img :src="image" alt="system image" class="w-24 h-24 object-contain mb-4" />
    <h3 class="text-lg font-semibold text-gray-700">
      {{ title }}
    </h3>
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
