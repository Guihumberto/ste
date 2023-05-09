<template>
  <section class="blog" id="blog">
    <h1 class="text-center">Plano para <span>Aprovação</span></h1>
    <h6 class="text-center">O que você vai aprender</h6>

    <div class="blog-content">
      <v-row justify="center">
        <v-col cols="12" sm="6" md="3" v-for="item, i in listPlanItems" :key="i">
          <div class="services-box">
            <v-icon>{{ item.icon }}</v-icon>
            <h3>{{ item.title}}</h3>
            <p>{{item.text}}
            </p>
          </div>
        </v-col>
      </v-row>
    </div>

  </section>
</template>

<script setup>
  const listPlanItems = [
    {id: 1, title:'Planejamento', text: 'Aprenda como fazer um planejamento para ser aprovado no mestrado sem perda de tempo.', img: '', icon: 'mdi-account-school-outline'},
    {id: 2, title:'Preparação', text: 'Saiba se mestrado é mesmo para você.', img: '', icon: 'mdi-lightbulb'},
    {id: 3, title:'Edital', text: 'Leia o edital com inteligência.', img: '', icon: 'mdi-chess-queen'},
    {id: 4, title:'Programa', text: 'Escolha o programa de pós-graduação certo.', img: '', icon: 'mdi-diamond-stone'},
    {id: 5, title:'Conquiste', text: 'Encante os melhores professores orientadores.', img: '', icon: 'mdi-school'},
    {id: 6, title:'Rumo certo', text: 'Aprenda a escolher tema do seu projeto de pesquisa.', img: '', icon: 'mdi-arrow-decision'},
    {id: 7, title:'Leitura', text: 'Conheça os tipos de leitura e pare de perder tempo com leituras inúteis', img: '', icon: 'mdi-bookshelf'}
  ]
</script>

<style scoped>
.blog {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  min-height: auto;
  background: var(--second-bg-color);
  padding: 10rem 7% 7rem;
  color: #fff;
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
}
.blog h1 span{
  color: var(--main-color);
}
.blog h6{
  font-size: 30px;
  margin-bottom: 5rem;
  transition: .5s;
}
.blog-content{
  max-width: 1200px;
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
  height: 70px;
}

@media (max-width: 991px){
  .blog h1{
    font-size: 40px;
  }
  .blog h6{
    font-size: 20px;
    margin-bottom: 5rem;
  }
}
</style>
