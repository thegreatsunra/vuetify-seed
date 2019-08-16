<template>
  <v-navigation-drawer
    v-model="drawerIsVisible"
    app
  >
    <v-list dense>
      <v-list-item to="home">
        <v-list-item-action>
          <v-icon>mdi-home</v-icon>
        </v-list-item-action>
        <v-list-item-content>
          <v-list-item-title>Home</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
      <v-list-item to="about">
        <v-list-item-action>
          <v-icon>mdi-help-circle</v-icon>
        </v-list-item-action>
        <v-list-item-content>
          <v-list-item-title>About</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  props: {
    isVisible: Boolean
  },
  data () {
    return {
      drawerIsVisible: null
    }
  },
  mounted () {
    this.$eventBus.$on('toggle-navigation-drawer', () => {
      this.drawerIsVisible = !this.drawerIsVisible
      console.log('drawer toggled')
    })
  },
  watch: {
    isVisible (value) {
      this.drawerIsVisible = value
    }
  }
}
</script>
