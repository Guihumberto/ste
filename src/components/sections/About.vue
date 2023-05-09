<template>
  <section class="about" id="about">
    <div class="about-img">
      <aboutImg />
    </div>
    <div class="about-content">
      <h1 class="heading">Sobre <span>mim</span></h1>
      <h3>Oi, Eu Posso Ajudar Você Com Seu Próximo Projeto!</h3>
      <p>
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ipsa ullam dolorem porro.
        Fuga tenetur possimus consectetur,
        facilis soluta consequatur repudiandae amet maxime fugiat accusamus! Aliquam porro est rem illo sunt.
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ipsa ullam dolorem porro.
      </p>
      <btnOne />
    </div>

  </section>
</template>

<script setup>
import aboutImg from '@/components/elements/about-img.vue'
import btnOne from '@/components/elements/btn-one.vue'
</script>

<style scoped>
section{
  min-height: 100vh;
  padding: 10rem 7% 5rem;
}
.about {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 4rem;
  background: var(--second-bg-color);
  color: #fff;
}

.about-img{
}
.about-content{
  max-width: 700px;
  margin: 0 50px;
}
.about-content h1{
  font-size: 4.5rem;
  font-weight: 700;
  color: #fff;
  line-height: 1.2;
  opacity: 0;
  animation: slideRight 1s ease forwards;
  animation-delay: .7s;
  text-align: left;
  line-height: 1.2;
}
.about-content h1 span{
  color: var(--main-color);
}
.about-content h3{
  font-size: 2rem;
}
.about-content p{
  font-size: 1.6rem;
  margin: 2rem 0 3rem;
}
@media (max-width: 890px) {
  section{
    min-height: 100vh;
    padding: 3rem 1% 2rem;
  }
  .about{
    flex-direction: column;
  }
  .about-img{
    width: 100%;
    display: flex;
    justify-content: center;
  }
  .about-content{
    text-align: center;
  }
  .about-content h1{
    text-align: center;
  }

}

</style>
