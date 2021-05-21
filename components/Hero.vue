<template>
    <div class="pb-15 mb-4">
      <!-- slider  -->
      <v-main class="slider">
        <v-carousel
            cycle
            height="500"
            hide-delimiter-background
            show-arrows-on-hover

          >
          <v-carousel-item
            v-for="(slide, i) in slides"
            :key="i"
            :src="slide.src"
          >
              <div id="row">
                  <span>New pic</span>
                  <h1>Thats the new pic</h1>
                  <v-btn>shop now</v-btn>
              </div>
          </v-carousel-item>
      </v-carousel>
    </v-main>

    </div>
</template>

<script>
export default {
  name: "Hero",
  data() {
    return {
      slides: [
        {
          src:  require("../assets/images/slider12.jpg"),
        },
        {
          src: require("../assets/images/slider11.jpg"),
        },
        {
          src: require("../assets/images/slider13.jpg"),
        },
        {
          src: require("../assets/images/slider10.jpg"),
        }
      ]
    };
  }
};
</script>
<style scoped>
 div#row {
    margin-top: 60px;
    padding: 100px;
}
</style>
