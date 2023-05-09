<template>
  <section id="home">
      <bubbles />
    <div class="home">
      <sci />
      <div class="home-content">
        <h1>Stephane <span>Lima</span></h1>
        <textTyping />
        <p>
         O plano estratégico para acelerar sua aprovação no mestrado em qualquer área sem perda de tempo.
        </p>
        <btnOne />
      </div>
      <homeImg/>
    </div>
  </section>
</template>

<script setup>
  import bubbles from '../elements/bubbles.vue';
  import btnOne from '@/components/elements/btn-one.vue'
  import sci from '@/components/elements/sci.vue'
  import homeImg from '@/components/elements/home-img.vue'
  import textTyping from '../elements/textTyping.vue';
</script>

<style scoped>
.home {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 70px 10% 0;
}
.home-content{
  max-width: 700px;
  margin: 0 50px;
}
.home-content h1{
  font-size: 56px;
  font-weight: 700;
  color: #000;
  line-height: 1.2;
  opacity: 0;
  animation: slideRight 1s ease forwards;
  animation-delay: .7s;
  transition: .5s;
}
.home-content h1 span{
  color: var(--main-color);
}
.home-content h3{
  font-size: 32px;
  font-weight: 700;
  opacity: 0;
  animation: slideLeft 1s ease forwards;
  animation-delay: 1s;
}
.home-content p{
  font-size: 16px;
  margin: 20px 0 40px;
  line-height: 1.7;
  opacity: 0;
  animation: slideLeft 1s ease forwards;
  animation-delay: 1.2s;
}
@media (max-width: 700px){
  .home{
    flex-direction: column-reverse;
    padding: 70px 3% 0;
    margin-top: 7rem;
  }
  .home-content{
    margin: 0px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .home-content h1{
    font-size: 40px;
  }
}
</style>
