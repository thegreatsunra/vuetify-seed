<template>
  <v-app-bar
    app
    color="indigo"
    dark
  >
    <v-app-bar-nav-icon @click.stop="$eventBus.$emit('toggle-navigation-drawer')"></v-app-bar-nav-icon>
    <v-toolbar-title>Application</v-toolbar-title>
  </v-app-bar>
</template>

<script>
export default {
  data () {
    return {
    }
  }
}
</script>
