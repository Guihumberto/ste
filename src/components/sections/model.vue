<template>
  <section class="comments" id="comments">
    <div class="comments-content">
      <h1>Sobre a <span>mentoria</span></h1>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.comments {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 70px 10% 0;
}
.comments-content{
  max-width: 700px;
  margin: 0 50px;
}
.comments-content h1{
  font-size: 56px;
  font-weight: 700;
  color: #000;
  line-height: 1.2;
  opacity: 0;
  animation: slideRight 1s ease forwards;
  animation-delay: .7s;
}
.comments-content h1 span{
  color: var(--main-color);
}

</style>
