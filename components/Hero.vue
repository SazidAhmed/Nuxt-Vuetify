<template>
    <div class="pb-15">
      <!-- slider  -->
        <v-carousel cycle hide-delimiters>
          <v-carousel-item
            v-for="(item,i) in items"
            :key="i"
            :src="item.src"
            reverse-transition="fade-transition"
            transition="fade-transition"
          >
            <v-row
                class="fill-height"
                align="center"
                justify="center"
              >
                <div class="display-3">
                  <h1 class="ma-3">new pic</h1>
                  <p class=" mt-5 ma-3">thats the new style</p>
                  <v-btn>Shop Now</v-btn>
                </div>
              </v-row>
          </v-carousel-item>
        </v-carousel>

    </div>
</template>

<script>
export default {
  name: "Hero",
  data() {
    return {
      items: [
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
