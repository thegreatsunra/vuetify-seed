<template>
  <v-app>
    <app-toolbar />
    <v-content>
      <hello-world />
    </v-content>
  </v-app>
</template>

<script>
import HelloWorld from '@/components/HelloWorld'
import AppToolbar from '@/components/AppToolbar'

export default {
  name: 'App',
  components: {
    HelloWorld,
    AppToolbar,
  },
  data () {
    return {
      //
    }
  }
}
</script>
