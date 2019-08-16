<template>
  <v-app>
    <app-nav-drawer :is-visible="appNavDrawerIsVisible" />
    <app-bar />
    <v-content>
      <hello-world />
    </v-content>
  </v-app>
</template>

<script>
import HelloWorld from '@/components/HelloWorld'
import AppNavDrawer from '@/components/AppNavDrawer'
import AppBar from '@/components/AppBar'

export default {
  name: 'App',
  components: {
    HelloWorld,
    AppNavDrawer
    AppBar,
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
