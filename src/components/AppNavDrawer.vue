<template>
  <v-navigation-drawer
    clipped
    fixed
    v-model="drawerIsVisible"
    app
    dark
  >
    <v-list>
      <v-list-tile @click="todo()">
        <v-list-tile-action>
          <v-icon>home</v-icon>
        </v-list-tile-action>
        <v-list-tile-title>Home</v-list-tile-title>
      </v-list-tile>
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
  watch: {
    isVisible (value) {
      this.drawerIsVisible = value
    },
    drawerIsVisible (value) {
      this.$eventBus.$emit('toggle-app-nav-drawer', value)
    }
  },
  methods: {
    todo () {
      console.log('TODO')
    }
  }
}
</script>
