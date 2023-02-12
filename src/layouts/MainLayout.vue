<template>
  <q-layout view="lHh Lpr lFf">
    <header-unex/>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'
import HeaderUnex from "components/HeaderUnex";

export default defineComponent({
  name: 'MainLayout',

  components: {
    HeaderUnex
  },
})
</script>
