<template>
  <v-app dark>
    <!-- navbar -->
    <v-app-bar
      fixed
      app
    >
      <v-toolbar-title v-text="title" />
      <!-- left -->
      <v-spacer />
      <!-- right -->
    </v-app-bar>
    <!-- Navbar End-->
    <v-main>
      <v-container>
        <!--content -->
        <nuxt />
        <!--content End-->
      </v-container>
    </v-main>
    <!-- footer -->
    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
    <!-- footer End-->
  </v-app>
</template>

<script>

export default {
  data () {
    return {
      fixed: false,
      title: 'Storefront'
    }
  }
}
</script>
