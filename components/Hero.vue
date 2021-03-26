<template>
  <div class="heroBlock">
    <v-container>
      <v-row wrap justify-space-between>
        <v-col cols="auto" lg="3">
          <div>Lorem ipsum dolor sit</div>
        </v-col>
        <v-col cols="5">
           <v-text-field
            flat
            solo-inverted
            show-details
            prepend-inner-icon="mdi-magnify"
            label="Search"
            class="hidden-sm-and-down"
          ></v-text-field>
        </v-col>
        <v-spacer></v-spacer>
        <v-col >
          <v-btn flat class="mt-3">
          <v-icon>mdi-cart</v-icon>
            my cart
          </v-btn>
        </v-col>
      </v-row>
    </v-container>

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
