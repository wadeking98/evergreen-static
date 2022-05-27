<template>
  <v-app>
    <AppHeader/>
    <v-main>
      <v-container :class="{ 'mt-10 mb-10': $vuetify.breakpoint.mdAndDown, 'mt-15': $vuetify.breakpoint.lgAndUp }">
        <Nuxt />
      </v-container>
    </v-main>
    <AppFooter/>
  </v-app>
</template>

<script>
import AppHeader from '../components/AppHeader.vue'
import AppFooter from '../components/AppFooter.vue'

export default {
  name: 'App',
  components: {
    AppHeader,
    AppFooter
  }
}
</script>
