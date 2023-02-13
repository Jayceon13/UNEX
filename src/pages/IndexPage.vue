<template>
  <q-page class="index-page">
      <div class="logo-unex">
        <div class="logo-block" v-if="$route.path !== '/services'">
          <img alt="" src="/img/logo.png">
        </div>
      </div>
      <div class="main-block">
        <h3>Доставка грузов из Китая и Европы
          в Россию, Казахстан, Узбекистан и Украину</h3>
      </div>
      <div class="services-block">
        <div class="sea-block">
            <video class="video-2" autoplay="autoplay" muted="muted" loop="loop" playsinline="playsinline" poster="/img/poster1.jpg" id="myVideo">
              <source src="/video/vdo.mp4" type="video/mp4">
            </video>
          <p>ДОСТАВКА МОРЕМ</p>
        </div>
        <div class="block-service-second">
        <div class="block-avia-broc">
          <div class="block-serv">
            <p>КОМПЛЕКСНОЕ ОБСЛУЖИВАНИЕ</p>
          </div>
          <div class="block-broc">

            <p>БРОКЕРСКИЕ УСЛУГИ</p>
          </div>
          <div class="block-avia" @click="blockAvia()">
            <video class="video-5" autoplay muted loop playsinline poster="/img/poster2.jpg" id="myVideo">
              <source src="/video/vdo1.mp4" type="video/mp4">
            </video>
            <p>АВИАДОСТАВКА</p>
          </div>
        </div>
        <div class="block-auto-save">
          <div class="block-auto">
            <video class="video-6" autoplay muted loop playsinline poster="/img/poster3.jpg" id="myVideo">
              <source src="/video/vdo2.mp4" type="video/mp4">
            </video>
            <p>АВТОДОСТАВКА</p>
          </div>
          <div class="block-save">
            <p>ХРАНЕНИЕ</p>
          </div>
        </div>
      </div>
      </div>
      <div class="block-about-us">
        <div class="logo-about">
          <div class="logo-about-us" v-if="$route.path !== '/services'">
            <img alt="" src="/img/logo.png">
          </div>
        </div>
        <div class="main-about">
        <h3><span style="color: #ff8562">UNEX LOGISTIC SYSTEMS -</span>
            <span style="color: #666666">КОЛОССАЛЬНЫЙ ОПЫТ И ВЫСОКОЕ КАЧЕСТВО</span>
        </h3>
        </div>
        <q-carousel
          v-model="slide"
          transition-prev="scale"
          transition-next="scale"
          swipeable
          animated
          control-color="white"
          navigation
          padding
          arrows
          class="bg-grey text-black shadow-1 rounded-borders"
          v-if="$q.screen.width <= 600">
            <q-carousel-slide name="block1" class="column no-wrap flex-center">
            <div class="block-inf">
              <p>Группа компаний UNEX была основана в 2001 году. Компания начинала свою деятельность
                на российском рынке, занимаясь импортом и экспортом полимерных материалов, стеклооснов и композитных составляющих</p>
            </div>
            <div class="block-inf">
              <p>Для наших клиентов мы предлагаем такие сроки доставки, какие не может гарантировать ни одна другая компания</p>
            </div>
            </q-carousel-slide>
            <q-carousel-slide name="block2" class="column no-wrap flex-center">
            <div class="block-inf">
              <p>Китай -> Казахстан -> РФ
                Авто/Авто

                18-22 дня
                Жд/Авто

                28-32 дня</p>
            </div>
            <div class="block-inf">
              <p>TEXT</p>
            </div>
            </q-carousel-slide>
          <q-carousel-slide name="block3" class="column no-wrap flex-center">
            <div class="block-inf">
              <p>TEXT</p>
            </div>
            <div class="block-inf">
              <p>TEXT</p>
            </div>
          </q-carousel-slide>
          <q-carousel-slide name="block4" class="column no-wrap flex-center">
            <div class="block-inf">
              <p>TEXT</p>
            </div>
            <div class="block-inf">
              <p>TEXT</p>
            </div>
          </q-carousel-slide>
        </q-carousel>
        <div class="information-block" v-else>
        <div class="about-information-1">
          <div class="block-inf">
            <p>Группа компаний UNEX была основана в 2001 году. Компания начинала свою деятельность
              на российском рынке.</p>
          </div>
          <div class="block-inf">
            <p>Китай -> Казахстан -> РФ
              Авто/Авто

              18-22 дня
              Жд/Авто

              28-32 дня</p>
          </div>
          <div class="block-inf">
            <p>TEXT</p>
          </div>
          <div class="block-inf">
            <p>TEXT</p>
          </div>
        </div>
        <div class="about-information-2">
          <div class="block-inf">
            <p>Для наших клиентов мы предлагаем такие сроки доставки, какие не может гарантировать ни одна другая компания</p>
          </div>
          <div class="block-inf">
            <p>TEXT</p>
          </div>
          <div class="block-inf">
            <p>TEXT</p>
          </div>
          <div class="block-inf">
            <p>TEXT</p>
          </div>
        </div>
      </div>
      </div>
    <div class="block-advantages">
      <div class="advantages-1">
        <div class="advantages-info-1">
        </div>
      </div>
      <div class="advanteges-2">
        <div class="advantages-info-2">
        </div>
        <div class="advantages-info-3">

        </div>
        <div class="advantages-info-4">

        </div>
      </div>
    </div>
    <avia-module v-model:show="showAvia"></avia-module>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'
import { ref } from 'vue'
import AviaModule from "components/AviaModule.vue";

export default defineComponent({
  name: 'IndexPage',
  components: {
    AviaModule
  },
  setup () {
    return {
      slide: ref('block1'),
    }
  },
  data() {
    return {
      showAvia: false,
    }
  },
  methods: {
    blockAvia() {
      this.showAvia = true;
    }
  }
})
</script>

<style scoped>
.video-2 {
  position: relative;
  width: 320px;
  height: 100%;
  object-fit: cover;
  z-index: -1;
  opacity: 1;
  border-radius: 30px;
}

.video-5 {
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: -1;
  opacity: 1;
  border-radius: 30px;
}
.video-6 {
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: -1;
  opacity: 1;
  border-radius: 30px;
}
.logo-unex{
  display: flex;
  height: 100px;
}
.logo-block img{
  padding: 20px;
  height: 100%;
  margin-left: 80px;
}
@media screen and (max-width: 720px){
  .logo-block img{
    margin-left: 30px;
  }
}
.main-block{
  width: 60%;
  margin-left: 100px;
  color: #666666;
}
@media screen and (max-width: 720px){
  .main-block{
    width: 100%;
    margin: 0;
    color: #666666;
    display: flex;
    text-align: center;
  }
  .main-block h3{
    font-size: 30px;
    margin: 30px;
    font-weight: bold;
  }
}
.block-service-second{
  width: 100%;
}
.sea-block{
  align-items: center;
  background: rgba(0, 0, 0, 0.5);
  height: 320px;
  justify-content: center;
  border-radius: 30px;
  display: flex;
  cursor: pointer;
}
.sea-block p{
  position: absolute;
}
.services-block {
  color: white;
  font-size: 20px;
  font-weight: bold;
  margin: 15px;
  align-self: flex-end;
}
@media screen and (min-width: 1000px){
  .block-avia-broc{
    height: 155px;
  }
  .block-auto-save{
    height: 155px;
  }
  .services-block{
    margin: 0 100px 0 100px;
  }
  .block-serv{
    width: 155px;
    margin-left: 10px;
    margin-right: 10px;
  }
  .block-broc{
    width: 155px;
    margin-left: 10px;
    margin-right: 10px;
  }
  .block-avia{
    margin-left: 10px;
    margin-right: 10px;
    width: 60%;
  }
  .block-auto{
    margin-left: 10px;
    margin-right: 10px;
    width: 80%;
  }
  .block-save{
    width: 155px;
    margin-left: 10px;
    margin-right: 10px;
  }
  .block-auto-save{
    margin-top: 10px;
  }
}
@media screen and (max-width: 1000px){
  .services-block{
    flex-flow: column;
    height: 100%;
  }
  .video-2{
    width: 100%;
  }
  .block-avia-broc{
    flex-flow: column;
    height: auto;
  }
  .block-service-second{
    height: auto;
  }
  .block-auto-save{
    flex-flow: column;
    height: auto;
  }
  .sea-block{
    margin: 10px 0 10px 0;
  }
  .block-avia{
    margin: 10px 0 10px 0;
  }
  .block-serv{
    width: 100%;
    margin: 10px 0 10px 0;
  }
  .services-block{
    margin: 15px 30px 15px 30px;
  }
  .block-broc{
    margin: 10px 0 10px 0;
    width: 100%;
  }
  .block-avia{
    margin: 10px 0 10px 0;
    width: 100%;
  }
  .block-auto{
    margin: 10px 0 10px 0;
    width: 100%;
  }
  .block-save{
    margin: 10px 0 10px 0;
    width: 100%;
  }
}
.services-block{
  display: flex;
}
.block-avia-broc{
  display: flex;
  overflow: hidden;
}
.block-auto-save{
  display: flex;
}
.block-serv{
  height: 155px;
  align-items: center;
  justify-content: center;
  background: #ff8562;
  display: flex;
  border-radius: 30px;
  text-align: center;
  cursor: pointer;
}
.block-serv p{
  display: contents;
  text-align: center;
  position: absolute;
  font-size: 15px;
}
.block-broc{
  height: 155px;
  align-items: center;
  justify-content: center;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  border-radius: 30px;
  text-align: center;
  cursor: pointer;
}
.block-broc p{
  display: contents;
  text-align: center;
  position: absolute;
  font-size: 15px;
}
.block-avia p{
  position: absolute;
}
.block-avia{
  align-items: center;
  justify-content: center;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  height: 155px;
  border-radius: 30px;
  cursor: pointer;
}
.block-auto{
  align-items: center;
  justify-content: center;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  height: 155px;
  border-radius: 30px;
  cursor: pointer;
}
.block-auto p{
  position: absolute;
}
.block-save{
  align-items: center;
  justify-content: center;
  background: #ff8562;
  display: flex;
  height: 155px;
  border-radius: 30px;
  cursor: pointer;
}
.block-save p{
  display: contents;
  text-align: center;
  position: absolute;
  font-size: 15px;
}
.block-about-us{
  display: flex;
  flex-flow: column;
  background: #f7f7f7;
}

@media screen and (min-width: 1000px){
  .block-about-us{
    margin-top: 30px;
    padding: 30px 100px 30px 100px;
    justify-content: center;
  }
  .main-about h3{
    display: flex;
    flex-flow: column;
    margin: 0;
    font-size: 35px;
    font-weight: bold;
  }
  .main-about{
    padding-left: 60px;
  }
  .logo-about{
    display: flex;
    width: 150px;
  }
  .logo-about-us img{
    width: 100%;
  }
  .information-block{
    justify-content: center;
    flex-flow: column;
  }
  .block-inf{
    margin: 20px;
  }
  .about-information-1{
    display: flex;
    justify-content: center;
  }
  .about-information-2{
    display: flex;
    justify-content: center;
  }
}
@media screen and (max-width: 1000px){
  .block-about-us{
    display: flex;
    flex-flow: column;
    justify-content: center;
  }
  .main-about h3{
    display: flex;
    flex-flow: column;
    margin: 0;
    font-size: 20px;
    text-align: center;
    font-weight: bold;
  }
  .logo-about{
    display: flex;
    width: 100%;
    justify-content: center;
  }
  .logo-about-us img{
    width: 155px;
  }
  .information-block{
    justify-content: center;
  }
  .about-information-1{
    display: flex;
    flex-flow: column;
  }
  .about-information-2{
    display: flex;
    flex-flow: column;
  }
  .block-inf{
    margin: 20px;
  }
}
@media screen and (max-width: 600px){
}
.main-about{
  justify-content: center;
  display: flex;
  width: 100%;
}
.information-block{
  display: flex;
}
.block-inf{
  width: 230px;
  height: 130px;
  background: white;
  border-radius: 30px;
  justify-content: center;
  text-align: center;
}
.block-advantages{
  display: flex;
}
.advantages-info-1{
  background-image: url("/img/china.jpg");
  background-size: cover;
}
.advantages-info-2{
  background-image: url("/img/office.jpg");
  background-size: cover;
}
.advantages-info-3{
  background-image: url("/img/china.jpg");
  background-size: cover;
}
.advantages-info-4{
  background-image: url("/img/office.jpg");
  background-size: cover;
}

@media screen and (min-width: 1000px){
  .block-advantages{
    justify-content: center;
  }
  .advantages-1{
    display: flex;
  }
  .advantages-info-1{
    width: 400px;
    margin: 20px;
  }
  .advantages-info-2{
    width: 400px;
    height: 200px;
    margin: 20px;
  }
  .advantages-info-3{
    width: 400px;
    height: 200px;
    margin: 20px;
    background-size: 340px;
  }
  .advantages-info-4{
    width: 400px;
    height: 200px;
    margin: 20px;
  }
}
@media screen and (max-width: 1000px){
  .block-advantages{

    flex-flow: column;
    justify-content: center;
    padding: 30px 30px 30px 30px;
    width: 100%;
  }
  .advantages-info-1{
    height: 200px;
    margin: 30px;
    background-position: 20%;
  }
  .advantages-info-2{
    height: 200px;
    margin: 30px;
    background-position: 20%;
  }
  .advantages-info-3{
    height: 200px;
    margin: 30px;
    background-position: 20%;
  }
  .advantages-info-4{
    height: 200px;
    margin: 30px;
    background-position: 20%;
  }
}
</style>
