<template>
  <section class="perfil" id="perfil">
    <h1 class="text">Stephane Lima</h1>
    <div class="wrapper-form">
      <p>Cadastre seu e-mail para promoções.</p>
      <v-form class="formulario">
        <v-text-field
          label="E-mail"
          variant="outlined"
          prepend-inner-icon="mdi-at"
          placeholder="Digite seu e-mail"
          density="compact"
          focused
          :rules="[
            (val) => isValidEmail(val) || 'Digite um endereço de e-mail válido',
          ]"
        ></v-text-field>
        <btn />
      </v-form>
    </div>
  </section>
</template>

<script setup>
import btn from '@/components/elements/btn-cad.vue'

const isValidEmail = email =>  {
    return String(email)
      .toLowerCase()
      .match(
        /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
      );
}

</script>

<style scoped>
.perfil {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background: linear-gradient(45deg,
    purple,
    rgb(104, 104, 173),
    #cd8d7b,
    #fbc490
  );
  background-size: 300% 300%;
  animation: colors 15s ease infinite;
}
@keyframes colors{
  0% {
    background-position: 0% 50%;
  }

  50%{
    background-position: 100% 50%;
  }

  100%{
    background-position: 0% 50%;
  }
}
.text{
  font-weight: 700;
  font-size: 4rem;
  color: #fff;
  border: 3px solid #fff;
  padding: 2rem 4rem;
  transition: .5s ease;
}
.text:hover{
  letter-spacing: 4px;
  border-top: 0px;
  border-right: 0px;
  text-shadow: 0 0 10px #0ef;
  animation: colorful 6s infinite;
}
@keyframes colorful {
  100%{
    filter: hue-rotate(360deg);
  }
}

.wrapper-form{
  margin-top: 5rem;
  text-align: center;
}
.wrapper-form p {
  font-size: 1.3rem;
  color: #fff;
  padding: .8rem 5px;
  max-width: 370;
}
.formulario{
  width: 390px;
  display: flex;
  justify-content: center;
  justify-items: center;
  gap: 10px;
}

@media (max-width: 768px) {
  .text{
    font-size: 2rem;
    font-weight: 500;
  }
  .formulario{
    flex-direction: column;
    padding-left: 5%;
    padding-right: 5%;
    gap: 0;
  }
}
</style>
