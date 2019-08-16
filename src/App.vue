<template>
  <v-app>
    <app-bar />
    <navigation-drawer :is-visible="navigationDrawerIsVisible" />
    <v-content>
      <router-view />
    </v-content>
  </v-app>
</template>

<script>
import AppBar from '@/components/AppBar'
import NavigationDrawer from '@/components/NavigationDrawer'

export default {
  name: 'App',
  components: {
    AppBar,
    NavigationDrawer
  },
  data () {
    return {
      navigationDrawerIsVisible: false
    }
  },
  mounted () {
    this.$eventBus.$on('toggle-navigation-drawer', value => {
      if (typeof value === 'undefined') {
        this.navigationDrawerIsVisible = !this.navigationDrawerIsVisible
      } else {
        this.navigationDrawerIsVisible = value
      }
    })
  }
}
</script>
