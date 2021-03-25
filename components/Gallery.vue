<template>
  <div class="block galleryBlock">
    <v-container>
      <v-row>
        <v-col v-for="item in items" :key="item.id" class="d-flex child-flex" cols="12" sm="4">
          <v-hover v-slot="{ hover }" open-delay="200" >
          <v-card flat tile class="d-flex mx-auto" :elevation="hover ? 16 : 100" :class="{ 'on-hover': hover }">
            <v-img :src="item.src" aspect-ratio="1" class="grey lighten-2">
              <template v-slot:placeholder>
                <v-row class="fill-height ma-0" align="center" justify="center">
                  <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
                </v-row>
              </template>
            </v-img>
          </v-card>
          </v-hover>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "Gallery",
  data() {
    return {
      items: [
        {
          id: 1,
          src: require("../assets/images/box1.jpg")
        },
        {
          id: 2,
          src: require("../assets/images/box2.png")
        },
        {
          id: 3,
          src: require("../assets/images/box3.png")
        },

      ]
    };
  }
};
</script>
