<template>
  <div class="container">
    <h2 class="title">{{ title }}</h2>
    <p class="description">{{ description }}</p>
    <h3 class="subtitle">{{ subtitle }}</h3>
    <ul>
      <li v-for="item in items" class="item" :key="item.id">{{ item.text }}</li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

interface Item {
  id: number;
  text: string;
}

const props = withDefaults(defineProps<{
  title?: string;
  subtitle?: string;
  description?: string;
  items: Item[];
}>(), {
  title: '功能说明',
  subtitle: '我做了什么',
  description: '',
  items: () =>[],
})

</script>

<style scoped>
.container {

}

.title {
  background: #1D2129;
  color: #fff;
  padding: 8px 12px;
  line-height: 1.2;
  border-radius: 8px;
  font-size: 20px;
  margin: 0 0 24px 0;
}

.description {
  font-size: 16px;
  margin: 0 0 24px 0;
}

.subtitle {
  font-size: 16px;
  margin: 0 0 8px 0;
  font-weight: 500;
}

.item {
  list-style: none;
  margin-left: 0;
  font-size: 14px;
  position: relative;
  padding-left: 20px;
  margin-bottom: 4px;
}

.item::before {
  content: '';
  position: absolute;
  left: 0;
  top: 50%;
  transform: translateY(-50%);
  width: 16px;
  height: 16px;
  background-image: url('/select.png');
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center;
}
</style>
