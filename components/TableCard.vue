<template>
  <div class="cards">
    <figure class="card">
      <div class="card-bg-wrapper"></div>
      <figcaption class="card-title">{{ title }}</figcaption>
      <p class="card-description">{{ description }}</p>
    </figure>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const props = defineProps({
  title: {
    default: "",
  },
  description: {
    default: "",
  },
});
</script>

<style scoped>
* {
  box-sizing: border-box;
}

.cards {
  perspective: 500px;
}

.card {
  width: 200px;
  height: 250px;
  border: 1px solid #1D2129;
  border-radius: 8px;
  position: relative;
  transform-style: preserve-3d;
  will-change: transform;
  transition: transform .5s;
}

.card-bg-wrapper {
  content: "";
  position: absolute;
  z-index: -1;
  top: 0;
  right: 0;
  height: 100%;
  width: 100%;
  border-radius: 6px;
  overflow: hidden;
}

.card-bg-wrapper:before {
  content: "";
  position: absolute;
  z-index: -1;
  top: -10px;
  right: -10px;
  background: #1D2129;
  height: 20px;
  width: 20px;
  border-radius: 10px;
  transform: scale(0);
  transform-origin: 50% 50%;
  transition: transform 0.25s ease-out;
}

.card:hover {
  transform: translateZ(5px) rotateX(10deg) rotateY(10deg);
}

.card:hover .card-bg-wrapper:before {
  transform: scale(40);
}

.card-title {
  color: #1D2129;
  position: absolute;
  top: 80px;
  left: 20px;
  transition: all .5s;
  font-size: 18px;
  font-weight: 500;
}

.card:hover .card-title {
  color: #fff;
  transform: translateZ(30px);
}

.card-description {
  color: #1D2129;
  position: absolute;
  top: 105px;
  left: 20px;
  right: 20px;
  font-size: 14px;
  font-weight: 400;
  transition: all .5s;
}

.card:hover .card-description {
  color: #fff;
  transform: translateZ(30px);
}
</style>
