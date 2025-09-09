<template>
  <h1 class="first-title">{{ text }}</h1>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const props = defineProps({
  text: {
    default: '',
  },
})

</script>

<style scoped>
.first-title {
  font-size: 48px;
  font-weight: 700;
  letter-spacing: 1px;
}
</style>
