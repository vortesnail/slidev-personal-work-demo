<template>
  <div class="container">
    <h2 class="title">{{ title }}</h2>
    <p class="description">{{ description }}</p>
    <h3 class="subtitle">{{ subtitle }}</h3>
    <ul class="items">
      <li v-for="item in items" class="item" :key="item.id">{{ item.text }}</li>
    </ul>
    <h3 class="subtitle-2">{{ subtitle2 }}</h3>
    <p class="data" v-html="data" />
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
  subtitle2?: string;
  data?: string;
  description?: string;
  items: Item[];
}>(), {
  title: '功能说明',
  subtitle: '我做了什么',
  subtitle2: '相关数据（昨日）',
  data: '',
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

.subtitle,
.subtitle-2 {
  font-size: 16px;
  margin: 0 0 8px 0;
  font-weight: 500;
}

.data {
  font-size: 16px;
  margin: 0 0 0 0;
}

.items {
  margin: 0 0 24px 0;
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
