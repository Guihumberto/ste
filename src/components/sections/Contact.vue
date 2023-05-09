<template>
  <section class="contact" id="contact">
    <div class="contact-content text-center">
      <h1>Fale <span>comigo</span></h1>
      <div class="formulario my-16">
        <v-form>
          <v-row>
            <v-col cols="12" sm="6" class="my-0 py-0">
              <v-text-field
                label="Nome Completo"
                variant="outlined"
                color="primary"
              ></v-text-field>
            </v-col>
            <v-col cols="12" sm="6" class="my-0 py-0">
              <v-text-field
                label="E-mail"
                variant="outlined"
                color="primary"
              ></v-text-field>
            </v-col>
            <v-col cols="12" sm="6" class="my-0 py-0">
              <v-text-field
                label="Celular"
                variant="outlined"
                color="primary"
              ></v-text-field>
            </v-col>
            <v-col cols="12" sm="6" class="my-0 py-0">
              <v-text-field
                label="Assunto"
                variant="outlined"
                color="primary"
              ></v-text-field>
            </v-col>
            <v-col cols="12" class="my-0 py-0">
              <v-textarea
                label="Sua Mensagem"
                variant="outlined"
                color="primary"
              ></v-textarea>
            </v-col>
          <v-col cols="12" class="text-center my-0 py-0" >
            <btn />
          </v-col>
        </v-row>
        </v-form>
        <span class="animate scroll" style="--i:2"></span>
      </div>
    </div>
  </section>
</template>

<script setup>
import btn from '@/components/elements/btn-form.vue'
</script>

<style scoped>
section{
  margin-top: 5rem;
  margin-bottom: 5rem;
}
.contact {
  min-width: 100%;
  min-height: 50vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0px 10% 0rem;
  background: var(--second-);
}
.contact-content{
  width: 880px;
  margin: 0 50px;
  border: 2px solid rgba(255, 255, 255, .5);
  border-radius: 25px;
  box-shadow: 0 25px 45px rgba(0, 0, 0, .2);
  padding: 30px 20px 0;
}
.contact-content h1{
  font-size: 56px;
  font-weight: 700;
  color: #000;
  line-height: 1.2;
  opacity: 0;
  animation: slideRight 1s ease forwards;
  animation-delay: .7s;
  transition: .5s;
}
.contact-content h1 span{
  color: var(--main-color);
}
@media (max-width: 991px) {
  .contact{
    padding: 0px 5% 0;
  }
  .contact-content{
    max-width: 880px;
    margin: 0 10px;
  }
  .contact-content h1{
    font-size: 40px;
  }
}
</style>
