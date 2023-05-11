<template>
  <section class="faq" id="faq">
    <h1>FAQ</h1>
    <h2>Perguntas <span>Frequentes</span></h2>
      <v-row class="services-row" style="max-width: 1080px;">
        <v-col cols="12" class="education-column" v-for="item, i in faqList.slice(0, 2)" :key="i">
          <div class="services-box">
            <div class="service-content">
              <div class="content">
                <h3>{{ item.title }}</h3>
                <p>{{ item.text }}
                </p>
              </div>
            </div>
          </div>
        </v-col>
      </v-row>
      <v-expand-transition>
        <v-row class="services-row animate" style="max-width: 1080px;" v-if="showList2">
          <v-col cols="12" class="education-column" v-for="item, i in faqList.slice(2, 8)" :key="i">
            <div class="services-box">
              <div class="service-content">
                <div class="content">
                  <h3>{{ item.title }}</h3>
                  <p>{{ item.text }}
                  </p>
                </div>
              </div>
            </div>
          </v-col>
        </v-row>
      </v-expand-transition>

      <div class="d-flex justify-center align-center w-100">
        <div style="position: relative;">
          <a @click.prevent="showList2 = !showList2" class="btnstyle">{{ btnName.name }}</a>
        </div>
      </div>
  </section >
</template>

<script setup>
import { ref, computed, watch } from 'vue'

  const showList2 = ref(false)
  const faqList = [
    {id: 1, title:'Serve para quem ainda não decidiu se quer fazer mestrado?',
      text: 'Com toda a certeza. É importante que você conheça o que significa entrar no mestrado e ter um panorama geral de todo o processo seletivo te ajudará inclusive a decidir se você quer se preparar e quando você deseja começar a preparação.'},
    {id: 2, title:'Serve para quem está na graduação?',
      text: 'A graduação pode ser uma oportunidade excelente para que você fortaleça seu currículo e entre no mestrado mais rapidamente. Assim, fazendo o Plano Para Aprovação, você conhecerá tudo o que precisa para passar no mestrado e poderá começar a se preparar ainda na graduação, saindo na frente dos demais. '},
    {id: 3, title:'Serve para quem ainda não sabe qual mestrado fazer?',
      text: 'Sim. Durante o método passamos exatamente por essas fases de definição e você terá clareza não só em qual instituição fazer o mestrado, mas com qual professor orientador e sobre qual tema de pesquisa.'},
    {id: 4, title:'Serve para quem ainda não tem edital aberto?',
      text: 'Com certeza. Preparar-se com o edital aberto é péssimo, pois você terá pouco tempo para se preparar. O ideal é começar antecipadamente.'},
    {id: 5, title:'Serve para quem não tem muito tempo?',
      text: 'Em uma manhã você conhecerá todo o método e terá o checklist para seguir de acordo com sua disponibilidade de tempo, portanto, se você tem pouco tempo, eu recomendo a compra pois te economiza muito tempo de pesquisas sozinhos on-line. '},
    {id: 6, title:'Eu vou ser aprovado necessariamente se seguir o checklist?',
      text: 'É impossível que qualquer um te garanta a aprovação, pois depende também de critérios subjetivos e dos concorrentes naquela vaga. O que posso te garantir é que você estará muito mais preparado seguindo o checklist do que se preparando sozinho.'},
    {id: 7, title:'Terão encontros ao vivo?',
      text: 'Não, o método é gravado para que você assista em sua velocidade e aplique-o imediatamente, com todas as aulas já disponíveis.'},
    {id: 8, title:'O curso ensina a fazer projeto de pesquisa?',
      text: 'Teremos uma aula sobre como fortalecer o projeto de pesquisa, mas o plano para aprovação não entra no detalhamento da elaboração do projeto. A ideia é dar uma visão ampla de todas as fases que serão enfrentadas para que você possa ter um passo a passo do que deve enfrentar. A parte de projeto e de escrita eu acompanho em minha mentoria acadêmica, com encontros quinzenais, ao vivo. Entre em contato para saber mais detalhes.'}
  ]

  const btnName = computed(() => {
    return showList2.value
    ? {icon: 'mdi-minus', name: '- Ver Menos'}
    : {icon: 'mdi-plus', name: '+ Ver Mais'}
  })

  watch(showList2, () => {
    window.location.href = "/#faq";
  })

</script>

<style scoped>
.faq {
  width: 100%;
  min-height: 50vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 70px 10% 5rem;
}
.faq-content{
  max-width: 700px;
  margin: 0 50px;
}
.faq h1{
  font-size: 56px;
  font-weight: 700;
  color: #000;
  line-height: 1.2;
  opacity: 0;
  animation: slideRight 1s ease forwards;
  animation-delay: .7s;
}
.faq h2{
  font-size: 30px;
  margin-bottom: 5rem;
  opacity: 0;
  animation: slideRight 1s ease forwards;
  animation-delay: 1s;
}
.faq h2 span{
  color: purple;
}
.faq-content h1 span{
  color: var(--main-color);
}

.services-box{
  position: relative;
  border-left: .2rem solid purple;
}
.service-content{
  position: relative;
  padding-left: 2rem;
}
.service-content::before{
  content: '';
  position: absolute;
  top: 0;
  left: -1.1rem;
  width: 2rem;
  height: 2rem;
  background: purple;
  border-radius: 50%;
}
.content{
  position: relative;
  padding: 1.5rem;
  border: .2rem solid purple;
  border-radius: .6rem;
  margin-bottom: 2rem;
  overflow: hidden;
  z-index: 1;
}
.content::before{
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 0;
  height: 100%;
  background: rgb(243, 223, 243);
  z-index: -1;
  transition: .5s;
}
.content:hover::before{
  width: 100%;
}
.year{
  font-size: 1.5rem;
  color: #00abf0;
  padding-bottom: .5rem;
}
.content h3{
  font-size: 2rem;
}
.content p{
  font-size: 1.6rem;
  padding-top: .5rem;
}
#services .services-box .animate.scroll {
  width: 105%;
}
#services.show-animate .animate.scroll{
  animation: showRight 1s ease forwards;
  animation-delay: calc(.3s * var(--i));
}
.animate {
  opacity: 1;
  animation: showRight 1s ease forwards;
}
@media (max-width: 771px) {
  .faq h1{
    font-size: 35px;
    font-weight: 700;
    color: #000;
    line-height: 1.2;
    opacity: 0;
    animation: slideRight 1s ease forwards;
    animation-delay: .7s;
  }
.faq h2{
    font-size: 20px;
    margin-bottom: 5rem;
  }
}

.btnstyle{
 position: relative;
 display: inline-flex;
 background: #fff;
 padding: 10px 20px;
 color: purple;
 border: 2px solid purple;
 border-radius: 15px;
 font-size: 20px;
 z-index: 1;
 overflow: hidden;
 transition: .5s;
}
.btnstyle::before{
 content: '';
 position: absolute;
 top: 0;
 left: 0;
 width: 0;
 background: purple;
 height: 100%;
 z-index: -1;
 transition: .5s;
}
.btnstyle:hover::before{
  width: 100%;
}
.btnstyle:hover {
  color: white
}
</style>
