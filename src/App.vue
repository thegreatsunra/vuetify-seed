<template>
  <v-app>
    <app-bar />
    <navigation-drawer :is-visible="appNavDrawerIsVisible" />
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
      appNavDrawerIsVisible: false
    }
  },
  mounted () {
    this.$eventBus.$on('toggle-app-nav-drawer', value => {
      if (typeof value === 'undefined') {
        this.appNavDrawerIsVisible = !this.appNavDrawerIsVisible
      } else {
        this.appNavDrawerIsVisible = value
      }
    })
  }
}
</script>
