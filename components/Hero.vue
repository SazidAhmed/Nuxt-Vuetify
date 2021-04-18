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
          src: "https://i.ytimg.com/vi/52kjz0YsG-c/maxresdefault.jpg",
        },
        {
          src: "https://i.ytimg.com/vi/Dc5R1DPcHqw/maxresdefault.jpg",
        },
        {
          src: "https://i.ytimg.com/vi/PZlX8tRxQ7o/maxresdefault.jpg",
        }
      ]
    };
  }
};
</script>
