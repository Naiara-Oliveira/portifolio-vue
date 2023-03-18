<template>
  <v-app>
    <v-main>
      <HomeView/>
    </v-main>
  </v-app>
</template>

<script>
import HomeView from './views/HomeView.vue'

export default {
  name: 'App',

  components: {
    HomeView
  },

  data: () => ({
    //
  }),
}
</script>
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
