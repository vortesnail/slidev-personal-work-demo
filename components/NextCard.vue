<template>
  <button class="border-2 border border-[#1D2129] bg-[#1D2129] hover:bg-white duration-300 relative group cursor-pointer hover:text-[#1d2129] text-white overflow-hidden w-[240px] max-h-[240px] p-2 flex justify-center items-center font-extrabold" @click="$nav.nextSlide">
    <div class="absolute -right-40 -top-40 z-10 w-40 h-40 rounded-full group-hover:scale-[6] duration-500 bg-[#8b5cf6]"></div>
    <p class="z-10 text-[28px] font-normal">支线任务</p>
  </button>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const props = defineProps({

})
</script>

<style scoped>

</style>