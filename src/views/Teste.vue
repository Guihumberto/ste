<template>
  <section>
    <div class="teste">
      <WordAnimate />
    </div>
  </section>
</template>

<script setup>
import WordAnimate from '@/components/testes/WordAnimate.vue';
</script>

<style scoped>
section{
  min-height: 100vh;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.teste{
  width: 1080px;
  height: 60vh;
  border: 2px solid blue;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
