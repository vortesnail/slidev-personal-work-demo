<template>
  <div class="container"></div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const props = defineProps({
  count: {
    default: 0,
  },
})

const counter = ref(props.count)
</script>

<style scoped>
.container {
}
</style>
