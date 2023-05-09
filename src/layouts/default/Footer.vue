<template>
  <div class="footer" id="footer">
    <div class="primary-footer">
      <div class="sec aboutus">
        <h2>Sobre a Sl Educar</h2>
        <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit.
          Voluptate reprehenderit consequatur dolor iste magni exercitationem commodi,
          facere perferendis earum? Quis est labore minus sequi. Dolore rerum facilis aspernatur vero quos.
        </p>
        <p class="mt-3">CNPJ: 37.535.343/0001-60</p>
        <ul class="sci">
          <li><a href=""><v-icon>mdi-instagram</v-icon></a></li>
          <li><a href=""><v-icon>mdi-youtube</v-icon></a></li>
          <li><a href=""><v-icon>mdi-whatsapp</v-icon></a></li>
          <li><a href=""><v-icon>mdi-email</v-icon></a></li>
        </ul>
      </div>
      <div class="sec quicklinks">
        <h2>Suporte</h2>
        <ul>
          <li><a href="">FAQ</a></li>
          <li><a href="">Ajuda</a></li>
        </ul>
      </div>
      <div class="sec quicklinks">
        <h2>Metodologia</h2>
        <!-- <ul>
          <li><a href=""></a></li>
          <li><a href=""></a></li>
          <li><a href=""></a></li>
          <li><a href=""></a></li>
        </ul> -->
      </div>
      <div class="sec contact">
        <h2>Fale comigo</h2>
        <ul class="info">
          <li>
            <v-icon class="pt-1">mdi-email</v-icon>
            <a href="mailto:suporte@stephanelima.com.br">suporte@stephanelima.com.br</a></li>
          <li>
            <v-icon class="pt-1">mdi-phone</v-icon>
            <a href="tel+9898888-4444">98 98888-4444</a></li>
            <li>
            <v-icon class="pt-1">mdi-instagram</v-icon>
            <a target="_blank" href="https://www.instagram.com/stephanelimab/">stephanelimab</a></li>
        </ul>
      </div>
    </div>
    <div class="second-footer">
      <p>&copy 2023 Sl Educar. Todos os Direitos Reservados.</p>
    </div>
  </div>
</template>

<script setup>

</script>

<style scoped>
.footer{
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  background: var(--bg-color);
  color: #fff;
}
.footer .primary-footer{
  width: 100%;
  display: grid;
  grid-template-columns: 2fr 1fr 1fr 1fr;
  grid-gap: 20px;
  padding: 50px 100px;
}
.footer .primary-footer .sec h2{
  position: relative;
  font-weight: 600;
  margin-bottom: 15px;
}
.footer .primary-footer .sec p{
  font-size: 1.3rem;
  max-width: 480px;
}
.footer .primary-footer .sci {
  margin-top: 20px;
  display: grid;
  grid-template-columns: repeat(4, 50px);
}
.footer .primary-footer .sci li{
  list-style: none;
}
.footer .primary-footer .sci a{
  display: inline-block;
  width: 36px;
  height: 36px;
  background: grey;
  display: grid;
  justify-content: center;
  align-content: center;
  text-decoration: none;
  color: #fff;
  font-size: 18px;
}
.footer .primary-footer .quicklinks{
  position: relative;
}
.footer .primary-footer .quicklinks ul li{
  list-style: none;
}
.footer .primary-footer .quicklinks ul li a{
  text-decoration: none;
  color: #fff;
  margin-bottom: 10px;
  display: inline-block;
  font-size: 1.3rem;
}
.footer .primary-footer .contact .info{
  position: relative;
}
.footer .primary-footer .contact .info li{
  display: grid;
  grid-template-columns: 30px 1fr;
  margin-bottom: 16px;
}
.footer .primary-footer .contact .info li a{
  text-decoration: none;
  color: #fff;
  font-size: 1.3rem;
}
.footer .second-footer{
  width: 100%;
  margin-top: 20px;
  padding: 20px 100px 20px;
  text-align: center;
  border-top: 1px solid rgba(221, 214, 214, 0.15);
  font-size: 1.5rem;
}

@media (max-width: 991px) {
  .footer .primary-footer{
    width: 100%;
    display: grid;
    grid-template-columns: repeat(2,1fr);
    grid-gap: 20px;
    }
  .footer .second-footer{
    padding: 20px 40px 30px;
  }
}
@media (max-width: 768px){
  .footer .primary-footer{
    width: 100%;
    display: grid;
    grid-template-columns: repeat(1,1fr);
    grid-gap: 20px;
    padding: 50px 30px;
  }
}
</style>
