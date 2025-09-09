<template>
  <div class="laptop">
    <div class="title" @click="isClick = !isClick">「Get笔记」桌面端</div>
    <div class="screen" :class="{ 'open': isClick }">
      <div class="header"></div>
      <div class="img">
        <img :src="desktop" alt="desktop" />
      </div>
    </div>
  <div class="keyboard"></div>
</div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import desktop from '../public/desktop.png'

const isClick = ref(false)
</script>

<style scoped>
.laptop {
  transform: scale(0.8);
}
.title {
  position: absolute;
  width: 100%;
  height: 100%;
  font-size: 24px;
  font-weight: 500;
  color: #1D2129;
  text-shadow: 0 0 5px #fff;
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 10px;
}
.screen {
  border-radius: 20px;
  box-shadow: inset 0 0 0 2px #c8cacb, inset 0 0 0 10px #000;
  height: 527px;
  /* height: 318px; */
  width: 777px;
  /* width: 518px; */
  margin: 0 auto;
  padding: 9px 9px 23px 9px;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  transform-style: preserve-3d;
  transform: perspective(1900px) rotateX(-89.5deg);
  transform-origin: 50% 100%;
}

.screen.open {
  animation: open 4s forwards;
}

@keyframes open {
  0% {
    transform: perspective(1900px) rotateX(-89.5deg);
  }
  100% {
    transform: perspective(1000px) rotateX(0deg);
  }
}
@keyframes hide {
  0% {
    width: 777px;
  }
  30% {
    width: 777px;
  }
  100% {
    width: 0;
  }
}
.screen::before {
  content: "";
  width: 777px;
  height: 12px;
  position: absolute;
  background: linear-gradient(#979899, transparent);
  top: -3px;
  transform: rotateX(90deg);
  border-radius: 5px 5px;
}
.screen.open::before {
  animation: hide 4s forwards;
}
.text {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  color: #fff;
  letter-spacing: 1px;
  text-shadow: 0 0 5px #fff;
}
.header {
  width: 100px;
  height: 12px;
  position: absolute;
  background-color: #000;
  top: 9px;
  left: 50%;
  transform: translate(-50%, -0%);
  border-radius: 0 0 6px 6px;
}
.img {
  width: 100%;
  height: 100%;
  overflow: hidden;
  border-radius: 13px 13px 0 0;
}
.img img {
  width: 100%;
  height: 100%;
}
.screen::after {
  background: linear-gradient(to bottom, #272727, #0d0d0d);
  border-radius: 0 0 20px 20px;
  bottom: 2px;
  content: "";
  height: 24px;
  left: 2px;
  position: absolute;
  width: 769px;
}
.keyboard {
  background: radial-gradient(circle at center, #e2e3e4 85%, #a9abac 100%);
  border: solid #a0a3a7;
  border-radius: 2px 2px 12px 12px;
  border-width: 1px 2px 0 2px;
  box-shadow: inset 0 -2px 8px 0 #6c7074;
  height: 24px;
  margin-top: -10px;
  position: relative;
  width: 1077px;
  z-index: 9;
}
.keyboard::after {
  background: #e2e3e4;
  border-radius: 0 0 10px 10px;
  box-shadow: inset 0 0 4px 2px #babdbf;
  content: "";
  height: 10px;
  left: 50%;
  margin-left: -60px;
  position: absolute;
  top: 0;
  width: 140px;
}
.keyboard::before {
  background: 0 0;
  border-radius: 0 0 3px 3px;
  bottom: -2px;
  box-shadow: -270px 0 #272727, 250px 0 #272727;
  content: "";
  height: 2px;
  left: 50%;
  margin-left: -10px;
  position: absolute;
  width: 60px;
}
</style>