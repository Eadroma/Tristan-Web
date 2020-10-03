<template>
    <v-app>
      <v-main>
       <NavBar />
       <Nuxt />
      </v-main>
    </v-app>
</template>
<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    Logo,
    VuetifyLogo
  }
}
</script>

<style>

</style>