<template>
  <v-toolbar
    app
    clipped-left
    fixed
    dark
    color="black"
  >
    <v-toolbar-side-icon
      @click="$eventBus.$emit('toggle-app-nav-drawer')"
    >
    </v-toolbar-side-icon>
    <v-toolbar-title>Vuetify Seed</v-toolbar-title>
    <v-spacer></v-spacer>
    <v-btn icon>
      <v-icon>person</v-icon>
    </v-btn>
  </v-toolbar>
</template>

<script>
</script>
