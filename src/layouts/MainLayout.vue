<template>
  <q-layout view="lHh Lpr lFf">
    <header-unex/>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
  <footer-unex/>
</template>

<script>
import { defineComponent, ref } from 'vue'
import HeaderUnex from "components/HeaderUnex";
import FooterUnex from "components/FooterUnex.vue";

export default defineComponent({
  name: 'MainLayout',

  components: {
    HeaderUnex,
    FooterUnex,
  },
})
</script>
