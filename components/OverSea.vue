<template>
  <div class="over-sea">
    <h1 class="title" :class="{ 'yes': yes }" @click="handleYes">
      <span>写作助手出海</span>
      <span v-if="!yes">❓</span>
      <span v-else>❕</span>
    </h1>
    <div class="cards">
      <div class="notification" :class="{ 'show': yes }">
        <div class="notiglow"></div>
        <div class="notiborderglow"></div>
        <div class="notititle">搭建项目框架</div>
        <div class="notibody">参与到产品技术选型、框架搭建、技术方案设计</div>
      </div>
      <div class="notification" :class="{ 'show': yes }">
        <div class="notiglow"></div>
        <div class="notiborderglow"></div>
        <div class="notititle">功能开发</div>
        <div class="notibody">参与到产品功能开发，适当提出交互方案</div>
      </div>
      <div class="notification" :class="{ 'show': yes }">
        <div class="notiglow"></div>
        <div class="notiborderglow"></div>
        <div class="notititle">产品打磨</div>
        <div class="notibody">参与到产品功能打磨，优化产品体验</div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const yes = ref(false)

const handleYes = () => {
  yes.value = true
}
</script>

<style scoped>
.over-sea {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.title {
  font-size: 2.25rem;
  color: #1D2129;
  transition: all 0.5s ease-in-out;
  position: absolute;
  left: 50%;
  top: 50%;
  z-index: 100;
  transform: translate(-50%, -50%);
}

.title.yes {
  top: 30%;
}

.cards {
  display: flex;
  flex-direction: row;
  gap: 24px;
}

.notification {
  flex-direction: column;
  isolation: isolate;
  position: relative;
  width: 14rem;
  height: 8rem;
  background: #29292c;
  border-radius: 0.5rem;
  overflow: hidden;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 16px;
  --gradient: linear-gradient(to bottom, #2eadff, #3d83ff, #7e61ff);
  --color: #32a6ff;
  transition: all 0.5s ease-in-out;
  transform: translateY(-60px);
  opacity: 0;
}

.notification.show {
  display: flex;
  transform: translateY(0);
  opacity: 1;
}

.notification:before {
  position: absolute;
  content: "";
  inset: 0.0625rem;
  border-radius: 0.9375rem;
  background: #18181b;
  z-index: 2
}

.notification:after {
  position: absolute;
  content: "";
  width: 0.25rem;
  inset: 0.65rem auto 0.65rem 0.5rem;
  border-radius: 0.125rem;
  background: var(--gradient);
  transition: transform 300ms ease;
  z-index: 4;
}

.notification:hover:after {
  transform: translateX(0.15rem)
}

.notititle {
  color: var(--color);
  padding: 0.65rem 0.25rem 0.4rem 1.25rem;
  font-weight: 500;
  font-size: 1.1rem;
  transition: transform 300ms ease;
  z-index: 5;
}

.notification:hover .notititle {
  transform: translateX(0.15rem)
}

.notibody {
  color: #99999d;
  padding: 0 1.25rem;
  transition: transform 300ms ease;
  z-index: 5;
}

.notification:hover .notibody {
  transform: translateX(0.25rem)
}

.notiglow,
.notiborderglow {
  position: absolute;
  width: 20rem;
  height: 20rem;
  transform: translate(-50%, -50%);
  background: radial-gradient(circle closest-side at center, white, transparent);
  opacity: 0;
  transition: opacity 300ms ease;
}

.notiglow {
  z-index: 3;
}

.notiborderglow {
  z-index: 1;
}

.notification:hover .notiglow {
  opacity: 0.1
}

.notification:hover .notiborderglow {
  opacity: 0.1
}

.note {
  color: var(--color);
  position: fixed;
  top: 80%;
  left: 50%;
  transform: translateX(-50%);
  text-align: center;
  font-size: 0.9rem;
  width: 75%;
}
</style>