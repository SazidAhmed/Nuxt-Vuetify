<template>
  <v-container>
      <!----details---->
      <v-row wrap justify-space-between>
        <v-col cols="auto" >
          <v-row wrap justify-space-between>
              <v-col cols="auto" >
                  <v-col v-for="cat in cats" :key="cat.id" cols="12">
                      <v-img
                            class="white--text align-end"
                            height="100%"
                            width="400"
                            :src="cat.src" >
                        </v-img>
                  </v-col>
              </v-col>
             <v-col cols="auto" >
               <v-col cols="auto">
                  <v-col v-for="top in tops" :key="top.id" cols="8" md="4">
                          <v-img
                              class="white--text align-end"
                              height="100%"
                              width="400"
                              :src="top.src">
                          </v-img>
                  </v-col>
             </v-col>
          </v-col>
        </v-row>
      </v-col>
        <v-col cols="auto">
           <div>
              <h2>afrin</h2>
                <div class="text-center">
                  <v-rating v-model="rating">
                    <template v-slot:item="props">
                      <v-icon
                        :color="props.isFilled ? genColor(props.index) : 'grey lighten-1'"
                        small
                        @click="props.click"
                      >
                        {{ props.isFilled ? 'mdi-star-circle' : 'mdi-star-circle-outline' }}
                      </v-icon>
                    </template>
                  </v-rating>
                </div>
               <div class="pa-2">৳ 1495</div>
           </div>
           <div class="pa-2">STOCK :
              <v-btn x-small color="green darken-1" dark>
                  in-stock
              </v-btn>
            </div>
           <div class="pa-2">CATEGORY : Dress</div>
           <div class="pa-2">TAGS: T-shirt</div>
           <div class="pa-2">SHARE :
                <v-icon>
                    mdi-facebook
                </v-icon>
                <v-icon>
                    mdi-twitter
                </v-icon>
                <v-icon>
                    mdi-linkedin
                </v-icon>
                <v-icon>
                    mdi-instagram
                </v-icon>
            </div>
           <v-btn class="mt-5" rounded color="deep-purple lighten-4"><NuxtLink to="/shoppingCart" style="text-decoration: none; color: inherit;">Add To Cart</NuxtLink></v-btn>
        </v-col>
      </v-row>
<!---colums--->
      <v-container class="grey lighten-5">
          <!-- product description -->
          <div class="container">
              <div class="text-center">
                    <v-btn text color="primary"><h3> Description</h3></v-btn>
                    <v-btn text color="primary"><h3> Additional Info</h3></v-btn>
                    <v-btn text color="primary"><h3> Review</h3></v-btn>
              </div>
          </div>
      </v-container>
        <v-container>
          <h2 class="text-center">Features Product</h2>
        </v-container>
  </v-container>
</template>

<script>
export default {
  name: "Login",
  data: () => ({

      cats: [
          {
            id: 1,
            src: require("../assets/images/feature1.jpg")
          }
        ],
      tops: [
          {
            id: 1,
            src: require("../assets/images/feature1.jpg")
          },
          {
            id: 2,
            src: require("../assets/images/feature7.jpg")
          },
          {
            id: 3,
            src: require("../assets/images/feature6.jpg")
          }
        ],
         colors: ['green', 'purple', 'orange', 'indigo', 'red'],
         rating: 1,

  }),
  methods: {
      genColor (i) {
        return this.colors[i]
      },
    },

};
</script>
<style>
  h3 {
    font-size: 25px;
}
i.v-icon.notranslate.mdi {
    color: rgb(30, 82, 30);
    cursor: pointer;
}
i.v-icon.notranslate.mdi:hover {
    color: red;

}
</style>
