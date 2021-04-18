<template>
  <v-app>
      <!-- navbar -->
      <Navbar />
      <!-- Navbar End-->
      <v-main>
              <!-- Main content -->
              <nuxt />
              <!--content End-->
      </v-main>
      <!-- footer -->
      <Footer />
      <!-- footer End-->
  </v-app>
</template>

<script>
import Navbar from "../components/website/Navbar";
import Footer from "../components/website/Footer";

export default {
  components: {
    Navbar,
    Footer,
  },

  data () {
    return {
      fixed: false,
      title: 'Storefront'
    }
  }
}
</script>
<style scoped>

</style>
