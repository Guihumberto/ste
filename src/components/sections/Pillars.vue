<template>
  <section class="pillars mx-auto" id="pillars">
    <h1>Os Cinco Pilares do Método para <br><span>Aprovação Antiestresse</span></h1>
    <div class="pillars-content">
      <h3 @mouseover="showBarMethod(1)" class="pillar1"><span></span>Mapeamento científico <br> da área de pesquisa</h3>
      <h3 @mouseover="showBarMethod(2)" class="pillar2"><span></span>Mapeando interesses <br>pessoais e expectativas</h3>
      <h3 @mouseover="showBarMethod(3)" class="pillar3"><span></span>Mapeando oportunidades <br> e condições reais</h3>
      <h3 @mouseover="showBarMethod(4)" class="pillar4"><span></span>Interesses do Programa <br> de pós graduação <br></h3>
      <h3 @mouseover="showBarMethod(5)" class="pillar5"><span></span>interesses do professores <br>orientadores</h3>

      <v-expand-transition>
        <div class="bannerInfo" v-show="showBaner">
          <h4>{{ itemPillar.title }}</h4>
          <p> {{ itemPillar.text }} </p>
          <br>
          <v-btn variant="text" @click="showBaner = false">Fechar</v-btn>
        </div>
      </v-expand-transition>

      <h2>
        Plano para <br> Aprovação <br> Antiestresse
      </h2>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

let showBaner = ref(false)
const listPillar = [
  {id: 1, title: 'Seus interesses pessoais e expectativas', text: 'Pois sem saber quem você é e o que você quer é impossível ter um plano que faça sentido para você.'},
  {id: 2, title: 'Os interesses do programa de pós-graduação', text: 'Para que você escolha o melhor programa para você e se prepare sabendo exatamente onde vai entrar.'},
  {id: 3, title: 'Os interesses do professor orientador', text: 'Para que você consiga ter um mestrado tranquilo e compatível com sua vida'},
  {id: 4, title: 'O mapeamento científico da área de pesquisa', text: 'Para que você crie uma pesquisa relevante.'},
  {id: 5, title: 'As oportunidade e condições reais', text: 'Para que você possa ter um plano prático e executável dentro da sua realidade.'},
]
let itemPillar = {id:0, title: '', text: '' }


const showBarMethod = (item) => {
  showBaner.value = false

  let list = listPillar.filter(x => x.id == item)[0]

  itemPillar.id = list.id
  itemPillar.title = list.title
  itemPillar.text = list.text

  showBaner.value = true

  setTimeout(() => {
  showBaner.value = false
}, 3000)
}



</script>

<style scoped>
section{
  min-height: auto;
  max-width: 1200px;
  margin-top: 5rem;
  margin-bottom: 5rem;
}
.pillars{
  display: flex;
  flex-direction: column;
  justify-content: center;
  justify-items: center;
  margin: 5rem 5rem 5rem;
}
.pillars h1{
  font-size: 50px;
  text-align: center;
  line-height: 1.2;
}
.pillars h1 span{
  color: purple;
}
.pillars-content{
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  margin-top: 5rem;
  height: 500px;
  color: #fff;
  background: linear-gradient(50deg, var(--second-bg-color), black, var(--second-bg-color));
  border: 5px solid purple;
}
.pillars-content h2{
  position: relative;
  font-size: 3rem;
  padding: 5px;
  border: 2px solid #fff;
  background: purple;
  border-radius: 5px;
  transition: .5s ease;
  color: #fff;
}
.pillars-content h2:hover {
  box-shadow: 0 .1rem 2rem rgb(99, 98, 98);
  transform: scale(1.05);
}
.pillars-content h3:hover {
  box-shadow: 0 .1rem 2rem rgb(99, 98, 98);
  transform: scale(1.05);
}
.pillars-content h3 {
  position: absolute;
  padding: 5px;
  margin: 5px;
  width: 160px;
  height: 160px;
  border-radius: 50%;
  font-size: 1.7rem;
  padding: 5px;
  border: 2px solid #fff;
  transition: .5s ease;
  display: flex;
  justify-content: center;
  align-items: center;
  background: var(--bg-color);
}
.pillars-content .pillar1{
  top: 0;
  left: 0;
  margin-top: 15px;
  margin-left: 15px;
}
.pillars-content .pillar2{
  bottom: 0;
  left: 0;
  margin-bottom: 15px;
  margin-left: 15px;
}
.pillars-content .pillar3{
  top: 0;
  right: 0;
  margin-top: 15px;
  margin-right: 15px;
}
.pillars-content .pillar4{
  top: 1;
  right: 0;
  margin-right: 180px;
}
.pillars-content .pillar5{
  bottom: 0;
  right: 0;
  margin-bottom: 15px;
  margin-right: 15px;
}
.pillar1 span, .pillar2 span {
  position: absolute;
  left: 0;
  margin-left: 100%;
  width: 50%;
  height: 4px;
  background: white;
  opacity: 0;
  transition: .5s;
}
.pillar1:hover span{
  opacity: 1;
}
.pillar2:hover span{
  opacity: 1;
}
.pillar3 span, .pillar4 span, .pillar5 span {
  position: absolute;
  right: 0;
  margin-right: 100%;
  width: 50%;
  height: 4px;
  background: white;
  opacity: 0;
  transition: .5s;
}
.pillar3:hover span{
  opacity: 1;
}
.pillar4:hover span{
  opacity: 1;
}
.pillar5:hover span{
  opacity: 1;
}
.bannerInfo{
  position: absolute;
  width: 480px;
  height: 300px;
  background: rgba(255, 255, 255, .1);
  border: 2px solid rgba(255, 255, 255, .5);
  border-right: 2px solid rgba(255, 255, 255, .2);
  border-left: 2px solid rgba(255, 255, 255, .2);
  backdrop-filter: blur(10px);
  border-radius: 25px;
  z-index: 1;
  box-shadow: 0 .1rem 2rem rgb(99, 98, 98);
  color: #fff;
  padding: 2rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  transition: .5s ease;
}
.bannerInfo h4{
  font-size: 2.7rem;
}
.bannerInfo p{
  font-size: 1.5rem;
}
@media (max-width: 700px) {
  .pillars-content {
    height: 280px;
  }
  .pillars h1{
    font-size: 35px;
  }
  .pillars-content h2{
    font-size: 1.1rem;
  }
  .pillars-content h3 {
    font-size: .9rem;
  }
  .bannerInfo{
    max-width: 400px;
    padding: 14px;
    max-height: 280px;
    background: purple;
    border: 2px solid rgba(255, 255, 255, .5);
    border-right: 2px solid rgba(255, 255, 255, .2);
    border-left: 2px solid rgba(255, 255, 255, .2);
  }
  .pillars-content h3 {
    margin: 5px;
    width: 90px;
    height: 90px;
  }
  .pillars-content .pillar4{
     margin-right: 15px;
  }
  .pillars-content .pillar3{
    top: 0;
    right: 0;
    margin-top: 2px;
    margin-right: 2px;
  }
  .pillars-content .pillar5{
    bottom: 0;
    right: 0;
    margin-bottom: 2px;
    margin-right: 2px;
  }
}

</style>
