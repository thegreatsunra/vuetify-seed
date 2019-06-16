<template>
  <v-navigation-drawer
    clipped
    fixed
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
  methods: {
    todo () {
      console.log('TODO')
    }
  }
}
</script>
