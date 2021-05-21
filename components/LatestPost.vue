<template>
  <div class="block latestPostBlock">
    <v-container>
      <h2 class="text-center">Latest Post</h2>
      <v-row wrap>
         <v-col v-for="item in items" :key="item.id" cols="12" md="3" >
           <v-hover>
              <template v-slot:default="{ hover }">
                <v-card class="mx-auto" width="200">
                        <v-img
                          class="white--text align-end"
                          height="100%"
                          :src="item.src"
                        >
                        </v-img>

                            <v-card-subtitle class="pb-0">{{ item.prize }}</v-card-subtitle>
                              <v-card-text class="text--primary">
                                 <div>{{ item.name }}</div>
                                 <div>{{item.category}}</div>
                              </v-card-text>
                              <v-card-action class="icon"><v-icon>mdi-home</v-icon></v-card-action>

                              <v-fade-transition>
                            <v-overlay
                              v-if="hover"
                              absolute
                              color="#036358"
                            >
                            <v-card-actions>
                                  <v-btn icon><NuxtLink to="/shoppingCart" style="text-decoration: none; color: inherit;"><v-icon>mdi-cart</v-icon></NuxtLink></v-btn>
                                  <v-btn icon><NuxtLink to="/Details" style="text-decoration: none; color: inherit;"><v-icon>mdi-eye</v-icon></NuxtLink></v-btn>
                              </v-card-actions>

                            </v-overlay>
                          </v-fade-transition>
                      </v-card>
                </template>
              </v-hover>
           </v-col>
        </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "LatestPost",
  data: () => ({
    show: false,
    items: [
      {
        id: 1,
        prize: "tk 1,000",
        name: "Top western road trips",
        category: "Three-pice",
        src: require("../assets/images/feature7.jpg")
      },
      {
        id: 2,
        prize: "tk 2,000",
        name: "Christmas tales to read",
        category: "Four-pice",
        src: require("../assets/images/three-pice2.jpg")
      },
      {
        id: 3,
        prize: "tk 3,000",
        name: "Top Western Dress",
        category: "Four-pice",
        src: require("../assets/images/three-pice4.jpg")
      },
      {
        id: 4,
        prize: "tk 3,000",
        name: "Top Western Dress",
        category: "Four-pice",
        src: require("../assets/images/three-pice4.jpg")
      },
       {
        id: 5,
        prize: "tk 1,000",
        name: "Top western road trips",
        category: "Three-pice",
        src: require("../assets/images/feature1.jpg")
      },
      {
        id: 6,
        prize: "tk 2,000",
        name: "Christmas tales to read",
        category: "Four-pice",
        src: require("../assets/images/feature7.jpg")
      },
       {
        id: 7,
        prize: "tk 1,000",
        name: "Top western road trips",
        category: "Three-pice",
        src: require("../assets/images/feature6.jpg")
      },
      {
        id: 8,
        prize: "tk 2,000",
        name: "Christmas tales to read",
        category: "Four-pice",
        src: require("../assets/images/three-pice2.jpg")
      },
       {
        id: 9,
        prize: "tk 1,000",
        name: "Top western road trips",
        category: "Three-pice",
        src: require("../assets/images/threepice1.jpg")
      },
      {
        id: 10,
        prize: "tk 2,000",
        name: "Christmas tales to read",
        category: "Four-pice",
        src: require("../assets/images/three-pice2.jpg")
      },
       {
        id: 11,
        prize: "tk 1,000",
        name: "Top western road trips",
        category: "Three-pice",
        src: require("../assets/images/threepice1.jpg")
      },
      {
        id: 12,
        prize: "tk 2,000",
        name: "Christmas tales to read",
        category: "Four-pice",
        src: require("../assets/images/three-pice2.jpg")
      },


    ],
  })
};
</script>
<style scoped>
h2.text-center {
    font-weight: bold;
    font-size: 40px;

}
</style>
