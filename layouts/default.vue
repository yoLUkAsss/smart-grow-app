import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'

<template>
  <v-layout class="rounded rounded-md">
    <!-- <v-navigation-drawer color="green" permanent></v-navigation-drawer> -->

    <v-app-bar :order="order" color="green-lighten-2" flat :title="barTitle" @click="goMain">

      <v-btn icon @click="sarasa">
        <v-icon>mdi-information-variant</v-icon>
      </v-btn>

    </v-app-bar>

    <v-main class="d-flex align-center justify-center" style="min-height: 800px">
      <slot></slot>
    </v-main>

  </v-layout>
  <AppFooter />
</template>

<script>

  export default {
    data: () => ({
      order: 0,
      barTitle: "Smart Grow App"
    }),
    methods: {
      sarasa: () => {
        console.log(this.$router)
        navigateTo('/about')
      },
      goMain: () => {
        navigateTo('/', {replace: true})
      }
    }
  }
</script>