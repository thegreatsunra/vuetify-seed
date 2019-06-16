<template>
  <v-app>
    <app-toolbar />
    <app-nav-drawer :is-visible="appNavDrawerIsVisible" />
    <v-content>
      <hello-world />
    </v-content>
  </v-app>
</template>

<script>
import HelloWorld from '@/components/HelloWorld'
import AppToolbar from '@/components/AppToolbar'
import AppNavDrawer from '@/components/AppNavDrawer'

export default {
  name: 'App',
  components: {
    HelloWorld,
    AppToolbar,
    AppNavDrawer
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
