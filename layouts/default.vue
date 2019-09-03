<template>
  <v-app class="grey lighten-4">
    <Navbar />
    <v-content class="mx-4 mb-4">
      <nuxt />
    </v-content>
    <v-footer fixed app>
      <span>&copy; 2019</span>
    </v-footer>
  </v-app>
</template>

<script>
import Navbar from '@/components/Navbar'

export default {
  components: { Navbar },
  data() {
    return {}
  }
}
</script>
