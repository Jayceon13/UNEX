<template>
  <div class="dialog" v-if="showSa" @click.stop="hideBlock">
    <div @click.stop class="dialog__content">
      <div class="x-icon-block">
        <img class="x-icon" @click="hideBlock" src="/icons/xicon.svg">
      </div>
      <div class="main-h">
        <h5>ФИНАНСОВАЯ ЛОГИСТИКА</h5>
      </div>
      <div class="block-p">
        <p>По вопросам финансовой логистики- обращаться напрямую к менеджеру.</p>
      </div>
      <div class="high-term">
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'SaveModule',
  props: {
    showSa: {
      type: Boolean,
      default: false,

    },
  },
  methods: {
    hideBlock() {
      this.$emit("update:showSa", false);
    },
  },
}
</script>

<style scoped>
.dialog {
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  display: flex;
}

.dialog__content {
  margin: auto;
  background: white;
  border-radius: 12px;
  min-height: 50px;
  max-width: 400px;
  justify-content: center;
}
h5{
  text-align: center;
  margin: 0;
  padding: 15px;
}
.high-term{
  display: flex;
}
.main-h{
  background: #ff7e46;
  color: white;
}
@media screen and (max-width: 600px){
  .dialog{
    justify-content: center;
  }
  .dialog__content{
    margin-left: 20px;
    margin-right: 20px;
  }
}
.x-icon-block{
  display: flex;
  justify-content: flex-end;
  margin: 20px;
}
.x-icon{
  width: 10px;
  height: 10px;
  cursor: pointer;
  z-index: 9999;
}
.block-p{
  margin: 20px;
}
.high-term{
  margin: 15px;
}
</style>

