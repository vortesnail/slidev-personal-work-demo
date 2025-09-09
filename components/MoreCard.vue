<template>
<div
  class="container w-[240px] max-h-[240px] bg-white border-2 border border-black p-9 space-y-3 relative overflow-hidden"
>
  <div v-if="order" class="w-24 h-24 bg-violet-500 rounded-full absolute -right-12 -top-12">
    <p class="absolute top-9 left-6 text-white text-2xl">{{ order }}</p>
  </div>
  <div class="fill-violet-500 w-12"></div>
  <h1 class="title font-bold text-[20px]">{{ title }}</h1>
  <p class="description text-sm text-zinc-500 leading-6">
    {{ description }}
  </p>
</div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const props = defineProps({
  order: {
    default: 0,
  },
  title: {
    default: '',
  },
  description: {
    default: '',
  },
})
</script>

<style scoped>
.container {
  transition: all 0.3s ease-in-out;
}

.container:hover {
  transform: translateY(-10px) rotate(-2deg);
}

.title {
  font-size: 24px;
  font-weight: 500;
  color: #1D2129;
}

.description {
  font-size: 16px;
  font-weight: 400;
  color: #1D2129;
}
</style>