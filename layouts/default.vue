<template>
  <v-app>
      <!-- navbar -->
      <Navbar />
      <!-- Navbar End-->
      <v-main>
          <v-container>
              <!-- Main content -->
              <nuxt />
              <!--content End-->
          </v-container>
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
