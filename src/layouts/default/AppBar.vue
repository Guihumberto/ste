<template>
  <header class="header" :class="menuShow ? 'bg-transparent':'headerDivsticky'">
    <a  @click="scroll('home')" class="logo" :class="showMenuSuspense ? 'text-purple':''">Stephane Lima</a>
    <nav class="navBar d-none d-sm-flex">
      <a
        v-for="item, i in menuList" :key="i"
        @click="scroll(item.path)"
        :class="item.path == idNameActiveSelect ? 'active' : ''"
        :style="`--i:${i+1}`"
      >{{ item.name }}</a>
    </nav>
    <v-spacer class="d-flex d-sm-none"></v-spacer>
      <v-btn
        @click="showMenuSuspense = !showMenuSuspense" id="menuBar"
        class="d-flex d-sm-none" variant="flat" color="transparent">
        <v-icon size="3.5rem" :color="showMenuSuspense ? 'purple':'black'">{{ showMenuSuspense ? 'mdi-close' : 'mdi-menu' }}</v-icon>
        <span class="animate" style="--i:2"></span>
      </v-btn>
  </header>
  <v-expand-transition>
      <div v-if="showMenuSuspense" class="menuSuspense d-flex d-sm-none">
        <v-list class="bg-transparent text-white w-100" nav>
          <v-list-item :prepend-icon="item.icon" v-for="item, i in menuList" :key="i" @click="scroll(item.path)" :class="idNameActiveSelect == item.path ? 'active':''">
            {{ item.name }}
          </v-list-item>
        </v-list>
      </div>
    </v-expand-transition>
    <div class="fixUpPage" v-show="!menuShow">
      <v-btn href="#home" color="success" size="5rem" icon="mdi-arrow-up"></v-btn>
    </div>
</template>

<script setup>
  import {ref, onMounted} from 'vue'
  const menuList = [
    {id: '1', name: 'Início', path: 'home', icon: 'mdi-home'},
    {id: '2', name: 'Mentoria', path: 'blog', icon: 'mdi-home'},
    {id: '3', name: 'Depoimentos', path: 'courses', icon: 'mdi-home'},
    {id: '4', name: 'Sobre', path: 'about', icon: 'mdi-information'},
    {id: '5', name: 'Contato', path: 'contact', icon: 'mdi-mail'},
  ]
  let showMenuSuspense = ref(false)
  let idNameActiveSelect = ref('home')
  let menuShow = ref(true)

  const scroll = (refName) => {
    const element = document.getElementById(refName)
    element.scrollIntoView({behavior: "smooth"})
    idNameActiveSelect.value = refName
    showMenuSuspense.value = false
  }

  onMounted(() => {
      let sections = document.querySelectorAll('section')
      window.onscroll = () => {
        //tranparencia da barra de menu
        if(window.scrollY > 50) {
          menuShow.value = false
        } else {
          menuShow.value = true
        }
        // incluir classe para animação
           sections.forEach(sec => {
            let id = sec.getAttribute('id')
            let top = window.scrollY
            let offset = sec.offsetTop - 100
            let heigth = sec.offsetHeight

            if(top >= offset && top < offset + heigth) {
              sec.classList.add('show-animate')
              switchActiveId(id)
            } else {
              sec.classList.remove('show-animate')
            }
           })
          //  animation footer on scroll
          let footer = document.querySelector('footer')
          if(footer) {
            footer.classList.toggle('show-animate', this.innerHeight + this.scrollY >= document.scrollingElement.scrollHeight)
            console.log(footer);
          }
      }
    })

  const switchActiveId = (value) => {
    switch(value) {
      case 'home':
        idNameActiveSelect.value = 'home'
        break;
      case 'about':
        idNameActiveSelect.value = 'about'
        break;
      case 'courses':
        idNameActiveSelect.value = 'courses'
        break;
      case 'blog':
        idNameActiveSelect.value = 'blog'
        break;
      case 'contact':
      idNameActiveSelect.value = 'contact'
        break;
      default:
        idNameActiveSelect.value = ''
    }
  }

  const trocaCor = () => {
    let header = document.querySelector('header')
    header.classList.remove('headerDivsticky')
    header.classList.add('trocaCor')
    header.classList.add('logoTrocaCor')
  }


</script>

<style>
.header{
  position: fixed;
  top: 0;
  width: 100%;
  padding: 20px 10%;
  display: flex;
  justify-content: center;
  align-items: center;
  background: transparent;
  z-index: 100;
  transition: .5s;
}
.headerDivsticky{
  background: #fff;
}
.trocaCor{
  background: var(--second-bg-color);
}
.logoTrocaCor {
  font-size: 25px;
  font-weight: 600;
  color: #fff;
  pointer-events: none;
  opacity: 0;
  animation: slideTop 1s ease forwards;
  transition: .5s;
}
.headerColor{
  background: var(--main-color);
}
.header .logo{
  font-size: 25px;
  font-weight: 600;
  color: #000;
  pointer-events: none;
  opacity: 0;
  animation: slideTop 1s ease forwards;
  transition: .5s;
}
.navBar a{
  display: inline-block;
  font-size: 18px;
  font-weight: 500;
  margin-left: 35px;
  color: #000;
  text-decoration: none;
  opacity: 0;
  animation: slideTop 1s ease forwards;
  animation-delay: calc(.2s * var(--i));
  transition: .5s ease;
}
.navBar .active,
.navBar a:hover{
  background: linear-gradient(45deg, #f06, #3cf);
  -webkit-text-fill-color: transparent;
  -webkit-background-clip: text;
}
.menuSuspense{
  position: fixed;
  top: 7rem;
  left: 0;
  width: 100%;
  padding: 1rem 4%;
  background: var(--main-color);
  box-shadow: 0 .5rem 1rem var(0, 0, 0, .2);
  font-size: 1.7rem;
  color: #fff;
  font-weight: 500;
  z-index: 100;
}
#menuBar{
  opacity: 0;
  animation: slideTop 1s ease forwards;
}
.fixUpPage{
  position: fixed;
  bottom: 5%;
  right: 10%;
  z-index: 100;
  transition: .5s ease;
}
@keyframes slideTop {
  0%{
    opacity: 0;
    transform: translateY(100px);
  }
  100%{
    opacity: 1;
    transform: translateY(0);
  }
}
@keyframes slideRight {
  0%{
    opacity: 0;
    transform: translateX(-100px);
  }
  100%{
    opacity: 1;
    transform: translateX(0);
  }
}
@keyframes slideLeft {
  0%{
    opacity: 0;
    transform: translateX(100px);
  }
  100%{
    opacity: 1;
    transform: translateX(0);
  }
}
@keyframes zoomIn {
  0%{
    opacity: 0;
    transform: scale(0);
  }
  100%{
    opacity: 1;
    transform: scale(1);
  }
}
@media (max-width: 570px){
  .header{
    padding-right: 1%;
    padding-left: 4%;
  }
}
/* @media (min-width: 1540px){
  .header{
    max-width: 1540px;
    left: 50%;
    transform: translateX(-50%);
  }
} */
</style>
