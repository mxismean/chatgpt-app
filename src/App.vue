<template>
  <div class="box">
    <h1 class="title">ChatGPT</h1>
    <p class="btn" @click="onEnter">OPEN</p>
  </div>
</template>

<script setup lang="ts">
import { onMounted } from 'vue';
const onEnter = () => {
  //
  window.location.href = 'https://chat.openai.com/chat';
};

onMounted(() => {
  // @ts-ignore
  // document.querySelector('html').style.zoom = 0.5;
});
</script>

<style scoped>
.box {
  width: 100%;
  height: 100%;
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  margin-top: -15%;
}
.title {
  position: relative;
  color: #6b6868;
  font-size: 120px;
  letter-spacing: 10px;
}
.title::after {
  content: 'ChatGPT';
  letter-spacing: 10px;
  top: 0;
  left: 0;
  position: absolute;
  color: transparent;
  background-image: linear-gradient(
    to left,
    rgb(0, 174, 255),
    rgb(0, 255, 85),
    rgb(212, 0, 255),
    rgb(0, 204, 255),
    rgb(238, 255, 0)
  );
  background-clip: text;
  -webkit-background-clip: text;
  clip-path: circle(80px at 0% 50%);
  animation: move 3s linear alternate infinite;
}
@keyframes move {
  0% {
    clip-path: circle(80px at 0% 50%);
  }
  100% {
    clip-path: circle(80px at 100% 50%);
  }
}
.btn {
  cursor: pointer;
  width: 150px;
  height: 50px;
  line-height: 50px;
  font-size: 30px;
  text-align: center;
  border-radius: 10px;
  background-image: linear-gradient(to left, #14f7e4, #c7ea19, #0e9595, #1e67ec, #1af0c2);
  background-size: 400%;
}
.btn:hover {
  animation: run 4s linear 0s infinite;
  transform: scale(1.1);
}
.btn:active {
  transform: scale(1);
}
@keyframes run {
  100% {
    background-position: 400% 0px;
  }
}
</style>
