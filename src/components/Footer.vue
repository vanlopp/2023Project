<template>
  <v-footer
    dark
    padless
    app
    inset
    
  >
    <v-card
      class="flex"
      flat
      tile
      color="#37936C"
      :elevation="10"
    >

      <v-card-text class="py-2 white--text text-center">
        {{ new Date().getFullYear() }} — <strong>J.F.Advance Med Co.,Ltd.</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>
