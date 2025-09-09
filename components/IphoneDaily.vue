<template>
  <div class="card">
    <div class="btn1"></div>
    <div class="btn2"></div>
    <div class="btn3"></div>
    <div class="btn4"></div>
    <div class="card-int">
      <video ref="videoRef" :src="dailyVideo" autoplay loop muted @click="togglePlay">
        <source :src="dailyVideo" type="video/mp4">
      </video>
    </div>
    <div class="play-pause-btn">
      <div v-if="!isPlaying" class="play-btn">
        <img :src="playBtn" alt="play" @click="togglePlay">
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import dailyVideo from '../public/daily.mov'
import playBtn from '../public/play.svg'
import pauseBtn from '../public/pause.svg'

const props = defineProps({
  text: {
    default: '',
  },
})

const videoRef = ref<HTMLVideoElement | null>(null)
const isPlaying = ref(true)

const togglePlay = () => {
  isPlaying.value = !isPlaying.value
  if (isPlaying.value) {
    videoRef.value?.play()
  } else {
    videoRef.value?.pause()
  }
}

</script>

<style scoped>
.card {
  width: 210px;
  height: 434px;
  background: black;
  border-radius: 35px;
  border: 2px solid rgb(40, 40, 40);
  padding: 7px;
  position: relative;
  box-shadow: 2px 5px 15px rgba(0, 0, 0, 0.486);
}

.card-int {
  height: 100%;
  border-radius: 25px;
  transition: all 0.6s ease-out;
  overflow: hidden;
  cursor: pointer;
}

.card:hover .card-int {
  background-position: 100% 100%;
}

.play-pause-btn {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 42px;
  height: 42px;
  border-radius: 50%;
  cursor: pointer;
}

.play-btn,.pause-btn {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  cursor: pointer;
}

.btn1, .btn2, .btn3, .btn4 {
  position: absolute;
  width: 2px;
}

.btn1, .btn2, .btn3 {
  height: 45px;
  top: 30%;
  right: -4px;
  background-image: linear-gradient(to right, #111111, #222222, #333333, #464646, #595959);
}

.btn2, .btn3 {
  transform: scale(-1);
  left: -4px;
}

.btn2, .btn3 {
  transform: scale(-1);
  height: 30px;
}

.btn2 {
  top: 26%
}

.btn3 {
  top: 36%
}
</style>
