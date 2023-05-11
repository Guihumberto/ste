<template>
  <section class="blog" id="blog">
    <h1 class="text-center">Mentoria</h1>

    <div class="blog-content">
      <div class="services-box" v-for="item, i in 3" :key="i">
        <v-icon>mdi-home</v-icon>
        <h3>Mentoria</h3>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Necessitatibus magni, placeat at,
          corrupti aliquid quod perferendis expedita quia, distinctio itaque enim quidem quos? Cum ratione
          ullam blanditiis doloremque perspiciatis molestiae?
        </p>
        <v-btn class="mt-5" color="purple">Novo</v-btn>
      </div>
    </div>

  </section>
</template>

<script setup>
</script>

<style scoped>
.blog {
  width: 100%;
  min-height: 100vh;
  background: var(--second-bg-color);
  padding: 10rem 7% 7rem;
  color: #fff;
}
.blog-content{
}
.blog h1{
  font-size: 56px;
  font-weight: 700;
  color: #fff;
  line-height: 1.2;
  opacity: 0;
  animation: slideRight 1s ease forwards;
  animation-delay: .7s;
  transition: .5s;
  margin-bottom: 5rem;
}
.blog h1 span{
  color: var(--main-color);
}
.blog-content{
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 2rem;
}
.services-box{
  flex: 1 1 30rem;
  padding: 3rem 2rem 4rem;
  border-radius: 2rem;
  box-shadow: 0 .1rem .5rem rgb(109, 104, 104);
  text-align: center;
  border-top: .6rem solid purple;
  border-bottom: .6rem solid purple;
  transition: .5s ease;
}

.services-box .v-icon {
  font-size: 7rem;
  color: purple;
}
.services-box h3 {
  font-size: 2.6rem;
  transition: .5s ease;
}
.services-box:hover h3 {
  color: purple;
}
.services-box:hover {
  box-shadow: 0 .1rem 2rem rgb(99, 98, 98);
  transform: scale(1.02);
}
.services-box p {
  font-size: 1.6rem;
  margin: 1rem 0 3rem;
}

@media (max-width: 991px){
  .blog h1{
    font-size: 40px;
  }
}
</style>
