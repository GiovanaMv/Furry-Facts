<template>
  <div class="card" :class="{ flipped: isFlipped }" @click="toggleFlip">
    <div class="card-inner">

      <div class="card-front">
        <img :src="image" :alt="name" />
        <h3>{{ name }}</h3>
      </div>

      <div class="card-back">
        <h3>{{ name }}</h3>
        <p>{{ description }}</p>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

defineProps<{
  name: string;
  image: string;
  description: string;
}>();

const isFlipped = ref(false);

function toggleFlip() {
  isFlipped.value = !isFlipped.value;
}
</script>

<style scoped>
.card {
  width: 100%;
  perspective: 800px;
  cursor: pointer;
}

@media (max-width: 768px){
  .card{
    height: 490px;
    display: grid;
  }
}
@media (min-width: 540px) and (max-width: 720px) {
  .card {
    height: 620px;
    width: 100%;
  }
}
@media (min-width: 768px) and (max-width: 1024px) {
    .card {
        width: 100%;
        height: 380px;
    }
}
@media (min-width: 912px) and (max-width: 1268px) {
  .card {
    height: 560px;
  }
}
@media (min-width: 1024px) and (max-width: 1366px) {
  .card {
    height: 480px;
    width: 90%;
  }
}

.card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  transform-style: preserve-3d;
  transition: transform 0.8s;
}
.card.flipped .card-inner {
  transform: rotateY(180deg);
}
.card-front,
.card-back {
  position: absolute;
  width: 100%;
  height: 90%;
  backface-visibility: hidden;
  border: 1px solid rgb(253, 226, 184);
  padding: 12px;
  box-sizing: border-box;
  border-radius: 8px;
  /* display: flex; */
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.card-front img {
  width: 100%;
  height: auto;
  border-radius: 8px;
}
.card-back {
  transform: rotateY(180deg);
  overflow-y: auto;
}
</style>