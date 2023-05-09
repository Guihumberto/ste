<template>
  <section class="payment" id="payment">
    <h1 class="text-center">Plano para <span>Aprovação</span></h1>
    <div class="content-payment">
      <v-row>
        <v-col cols="12" sm="4" v-for="item, i in 3" :key="i" >
          <div class="card ">
            <h2>R$ 999 <span>,99</span></h2>
            <p><v-icon>mdi-check</v-icon> Aulas Gravadas</p>
            <p><v-icon>mdi-check</v-icon> 5 Mapas Mentais</p>
            <p><v-icon>mdi-check</v-icon> Checklist Personalizável</p>
            <btn class="mt-12" />
          </div>
        </v-col>
      </v-row>
    </div>
  </section >
</template>

<script setup>
import btn from '@/components/elements/btn-form.vue'
</script>

<style scoped>
.payment {
  width: 100%;
  min-height: 50vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 70px 10% 5rem;
}
.payment-content{
  max-width: 700px;
  margin: 0 50px;
}
.payment h1{
  font-size: 56px;
  font-weight: 700;
  color: #000;
  line-height: 1.2;
  opacity: 0;
  animation: slideRight 1s ease forwards;
  animation-delay: .7s;
  margin-bottom: 5rem;
}
.payment h1 span{
  color: purple;
}
.payment-content h1 span{
  color: var(--main-color);
}
.card{
  position: relative;
  background: #d7dfe240;
  margin: 20px;
  width: 250px;
  height: 350px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  transition: all .4s;
  box-shadow: 1px 1px 10px #bdbdbd;
  overflow: hidden;
  border: 1px solid #fff;
  border-radius: 5px;
}
.card::before{
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100px;
  background: purple;
  z-index: 1;
}
.card::after{
  content: '';
  position: absolute;
  top: 90px;
  left: -30px;
  width: 200px;
  height: 40px;
  background: #fff;
  color: #000;
  transform-origin: left;
  transform: rotate(-45deg);
  text-align: center;
  z-index: 15;
  transition: all .4s;
}
.card:hover::after{
  background: #00d100;
  color: #000;
}

.card:hover{
  transform: scale(1.2);
}
.card h2{
  margin: 20px 0;
  z-index: 10;
  color: #fff;
}
.card p{
  margin: 10px 0;
}
.card .btn{
  width: 120px;
  height: 35px;
  cursor: pointer;
  background: rgb(0, 209, 0);
  border: none;
  color: #fff;
  transition: all .4s;
}
.btn:hover{
  background: #099df2;
}
@media (max-width: 700px) {
  .payment h1{
    font-size: 35px;
  }
}
</style>
