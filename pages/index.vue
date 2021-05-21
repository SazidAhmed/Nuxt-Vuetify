<template>
  <v-container>
    <Hero />
    <Gallery />
    <LatestPost />
  </v-container>
</template>

<script>
import Hero from "../components/Hero";
import Gallery from "../components/Gallery";
import LatestPost from "../components/LatestPost";



export default {
  name: "Home",

  components: {
    Hero,
    Gallery,
    LatestPost,

  }
};
</script>
