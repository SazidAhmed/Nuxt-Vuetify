<template>
    <div>
      <!-- slider  -->
      <v-row class="mt-2 mb-2">
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
                  <h1 >new pic</h1>
                  <p>thats the new style</p>
                  <v-btn>Shop Now</v-btn>
                </div>
              </v-row>
          </v-carousel-item>
        </v-carousel>
      </v-row>
    </div>
</template>

<script>
export default {
  name: "Hero",
  data() {
    return {
      items: [
        {
          src: require("../assets/images/slider-3.jpg"),
        },
        {
          src: require("../assets/images/slider-images.jpg"),
        },
        {
          src: require("../assets/images/slider2.jpg"),
        }
      ]
    };
  }
};
</script>
