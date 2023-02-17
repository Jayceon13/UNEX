<template>
  <q-page class="index-page">
      <div class="logo-unex">
        <div class="logo-block" v-if="$route.path !== '/services'" style="opacity: 1;">
          <img alt="" src="/icons/UnexGroup.png">
        </div>
      </div>
      <div class="main-block" >
        <h3>Оказываем услуги по транспортной и финансовой логистике.</h3>
      </div>
      <div class="services-block" >
        <div class="sea-block" @click="blockSea()">
            <video class="video-2" autoplay="autoplay" muted="muted" loop="loop" playsinline="playsinline" poster="/img/poster1.jpg" id="myVideo">
              <source src="/video/vdo.mp4" type="video/mp4">
            </video>
          <p>ДОСТАВКА ГРУЗОВ ПОД КЛЮЧ</p>
          <img class="hand" src="/icons/hand.svg">
        </div>
        <div class="block-service-second" >
        <div class="block-avia-broc">
          <div class="block-avia" @click="blockAvia()">
            <video class="video-5" autoplay muted loop playsinline poster="/img/poster2.jpg" id="myVideo">
              <source src="/video/vdo1.mp4" type="video/mp4">
            </video>
            <p>ТРАНСПОРТНАЯ ЛОГИСТИКА</p>
          </div>
          <div class="block-auto" @click="blockAuto()">
            <video class="video-6" autoplay muted loop playsinline poster="/img/poster4.jpg" id="myVideo">
              <source src="/video/vdo3.mp4" type="video/mp4">
            </video>
            <p>ФИНАНСОВАЯ ЛОГИСТИКА</p>
          </div>
        </div>
      </div>
      </div>
      <div class="block-about-us">
        <div class="logo-about">
          <div class="logo-about-us" v-if="$route.path !== '/services'">
            <img alt="" src="/icons/UnexGroup.png">
          </div>
        </div>
        <div class="main-about">
          <h3>Доставляем грузы из стран СНГ, Турции и Китая в Россию.</h3>
        </div>
        <div class="blocks-countries">
          <div class="countries-block-1">
            <p>РОССИЯ</p>
          </div>
          <div class="countries-block-2">
            <p>УЗБЕКИСТАН</p>
          </div>
          <div class="countries-block-3">
            <p>КЫРГЫЗСТАН</p>
          </div>
          <div class="countries-block-4">
            <p>ТУРЦИЯ</p>
          </div>
          <div class="countries-block-5">
            <p>КАЗАХСТАН</p>
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
    <avia-module v-model:showAv="showAvia"></avia-module>
    <auto-module v-model:showAu="showAuto"></auto-module>
    <broc-module v-model:showBr="showBroc"></broc-module>
    <save-module v-model:showSa="showSave"></save-module>
    <sea-module v-model:showSe="showSea"></sea-module>
    <serv-module v-model:show="showServ"></serv-module>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'
import { ref } from 'vue'
import AviaModule from "components/AviaModule.vue";
import BrocModule from "components/BrocModule.vue";
import AutoModule from "components/AutoModule.vue";
import SaveModule from "components/SaveModule.vue";
import SeaModule from "components/SeaModule.vue";
import ServModule from "components/ServModule";

export default defineComponent({
  name: 'IndexPage',
  components: {
    AviaModule,
    AutoModule,
    SeaModule,
  },
  setup () {
    return {
      slide: ref('block1'),
    }
  },
  data() {
    return {
      showAvia: false,
      showAuto: false,
      showSea: false,
    }
  },
  methods: {
    blockAvia() {
      this.showAvia = true;
    },
    blockAuto() {
      this.showAuto = true;
    },
    blockSea() {
      this.showSea = true;
    },
  }
})
</script>

<style scoped>
.hand{
  position: absolute;
  width: 20px;
  margin-top: 200px;
  animation: up-hand 1.5s ease-in-out infinite;
}
@keyframes up-hand {
  0% {
    opacity: 0;
  }
  50%{
    opacity: 1;
  }
  100%{
    opacity: 0;
  }
}
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
    width: 300px;
    height: auto;
  }
}
.main-block{
  justify-content: space-around;
  margin: 0 100px 0 100px;
  color: #666666;
  display: flex;
}
.main-block h3{
  font-size: 40px;
  font-weight: bold;
}
.main-about h3{
  color: #666666;
  font-size: 40px;
  font-weight: bold;
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
  .main-about h3{
    color: #666666;
    font-size: 30px;
    font-weight: bold;
    text-align: center;
  }
}
.block-service-second{
  width: 100%;
  display: flex;
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
  text-align: center;
  width: min-content;
}
.blocks-countries{
  display: flex;
  justify-content: space-between;
}
.blocks-countries p{
  font-size: 24px;
  font-weight: bold;
}
.countries-block-1{
  height: 200px;
  background-image: url('/img/Group11.svg');
  background-size: cover;
  background-position: center center;
  border-radius: 30px;
  margin: 10px;
  width: 200px;
  justify-content: center;
  display: flex;
  align-items: center;
  color: #ff7e46;
}
.countries-block-2{
  height: 200px;
  background-image: url('/img/Group12.svg');
  background-size: cover;
  background-position: center center;
  border-radius: 30px;
  margin: 10px;
  width: 200px;
  justify-content: center;
  display: flex;
  align-items: center;
  color: #666666;
}
.countries-block-3{
  height: 200px;
  width: 200px;
  background-image: url('/img/Group13.svg');
  background-size: cover;
  background-position: center center;
  border-radius: 30px;
  margin: 10px;
  justify-content: center;
  display: flex;
  align-items: center;
  color: #ff7e46;
}
.countries-block-4{
  height: 200px;
  width: 200px;
  background-image: url('/img/Group14.svg');
  background-size: cover;
  background-position: center center;
  border-radius: 30px;
  margin: 10px;
  justify-content: center;
  display: flex;
  align-items: center;
  color: #666666;
}
.countries-block-5{
  height: 200px;
  width: 200px;
  background-image: url('/img/Group15.svg');
  background-size: cover;
  background-position: center center;
  border-radius: 30px;
  margin: 10px;
  justify-content: center;
  display: flex;
  align-items: center;
  color: #ff7e46;
}


@media screen and (max-width: 1000px) {
  .blocks-countries{
    margin: 30px;
    flex-flow: column;
  }
  .countries-block-1{
    width: 100%;
    margin: 10px 0 10px 0;
  }
  .countries-block-2{
    width: 100%;
    margin: 10px 0 10px 0;
  }
  .countries-block-3{
    width: 100%;
    margin: 10px 0 10px 0;
  }
  .countries-block-4{
    width: 100%;
    margin: 10px 0 10px 0;
  }
  .countries-block-5{
    width: 100%;
    margin: 10px 0 10px 0;
  }
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
    height: 320px;
    display: flex;
    flex-flow: column;
    justify-content: space-between;
    width: 100%;
  }
  .services-block{
    margin: 0 100px 0 100px;
  }
  .block-avia{
    margin-left: 10px;
    margin-right: 10px;
    width: auto;
  }
  .block-auto{
    margin-left: 10px;
    margin-right: 10px;
    width: auto;
  }
  .main-block{
    width: 60%;
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
    width: 100%;
    margin-right: 10px;
  }
  .block-service-second{
    height: auto;
    margin-bottom: 25px;
  }
  .sea-block{
    margin: 10px 0 10px 0;
  }
  .block-avia{
    margin: 10px 0 10px 0;
  }
  .services-block{
    margin: 15px 30px 15px 30px;
  }
  .block-avia{
    margin: 10px 0 10px 0;
    width: 100%;
    text-align: center;
  }
  .block-avia p{
    font-size: 20px;
  }
  .block-auto{
    margin: 10px 0 0 0;
    width: 100%;
    text-align: center;
  }
  .block-auto p{
    font-size: 20px;
    text-align: center;
    padding: 10px;
  }
  .block-save p{
    font-size: 15px;
  }
  .main-block{
    flex-flow: column;
  }
}
.services-block{
  display: flex;
}
.block-avia-broc{
  display: flex;
  overflow: hidden;
}
.block-serv p{
  display: contents;
  text-align: center;
  position: absolute;
  font-size: 15px;
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
.block-save p{
  display: contents;
  text-align: center;
  position: absolute;
  width: min-content;
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
  .main-about{
    width: 70%;
  }
  .logo-about{
    display: flex;
    width: 250px;
    padding: 20px;
  }
  .logo-about-us img{
    width: 100%;
  }
}
@media screen and (max-width: 1000px){
  .block-about-us{
    display: flex;
    flex-flow: column;
    justify-content: center;
  }
  .logo-about{
    display: flex;
    width: 100%;
    justify-content: center;
    padding: 20px;
  }
  .logo-about-us img{
    width: 155px;
  }
}
.main-about{
  justify-content: center;
  display: flex;
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
