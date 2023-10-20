<template>
  <v-footer class="black text-center d-flex flex-column">

    <div>
      <v-btn v-for="icon in icons" :key="icon" class="mx-4" :icon="icon" variant="text" />
    </div>

    <div class="pt-0"> Lucas Sandoval </div>

    <v-divider></v-divider>

    <div>
      {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
    </div>
  </v-footer>
  
</template>

<script>
  export default {
    data: () => ({
      icons: [
        // 'mdi-facebook',
        // 'mdi-twitter',
        // 'mdi-linkedin',
        // 'mdi-instagram',
      ],
    }),
  }
</script>