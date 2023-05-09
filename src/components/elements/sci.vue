<template>
  <div class="wrapper-sci">
    <div class="home-sci">
      <a href=""><v-icon>mdi-instagram</v-icon></a>
      <a href=""><v-icon>mdi-whatsapp</v-icon></a>
      <a href=""><v-icon>mdi-youtube</v-icon></a>
    </div>
  </div>
</template>

<script setup>

</script>

<style  scoped>
.home-sci a{
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  font-size: 20px;
  color: #fff;
  text-decoration: none;
  margin: 20px 0;
  z-index: 1;
}
.home-sci a:nth-child(1){
  opacity: 0;
  animation: slideBottom 1s ease forwards;
  animation-delay: 2.1s;
}
.home-sci a:nth-child(2){
  opacity: 0;
  animation: slideRight 1s ease forwards;
  animation-delay: 2.1s;
}
.home-sci a:nth-child(3){
  opacity: 0;
  animation: slideTop 1s ease forwards;
  animation-delay: 2.1s;
}
.home-sci a::before{
  content: '';
  position: absolute;
  width: 100%;
  height: 100%;
  background: linear-gradient(45deg, #f06, #3cf);
  border-radius: 50%;
  z-index: -1;
  transition: .5s ease;
}
.home-sci a::after{
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #0c1022;
  border-radius: 50%;
  transform: scale(.88);
  z-index: -1;
  transition: .5s ease;
}
.home-sci a:hover::after{
  transform: scale(0);
}
.home-sci a:hover::before{
  filter: blur(5px);
}
@keyframes slideBottom {
  0%{
    opacity: 0;
    transform: translateY(-100px);
  }
  100%{
    opacity: 1;
    transform: translateY(0);
  }
}
@media (max-width: 700px){
  .wrapper-sci{
    display: flex;
    justify-content: center;
    margin-top: 10px;
  }
  .home-sci{
    position: relative;
    display: flex;
    left: 50%;
    bottom: 0;
    transform: translate(-50%);
    width: 100%;
  }
  .home-sci a{
    margin: 20px;
  }
}

</style>
