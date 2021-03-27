<template>
  <v-main>
    <Hero />
    <Gallery />
    <LatestPost />
    <Features />
    <BestSellings />
  </v-main>
</template>

<script>
import Hero from "../components/Hero";
import Gallery from "../components/Gallery";
import LatestPost from "../components/LatestPost";
import Features from "../components/Features";
import BestSellings from "../components/BestSellings";


export default {
  name: "Home",

  components: {
    Hero,
    Gallery,
    LatestPost,
    Features,
    BestSellings
  }
};
</script>
