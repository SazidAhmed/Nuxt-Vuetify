<template>
<v-container>
  <v-row
      class="mb-4"
      no-gutters
    >
      <v-col cols="6" md="4">
        <v-card
          class="pa-4"
          outlined
          tile
        >
          <h2>Search Products</h2>
          <v-text-field
          flat
          solo-inverted
          hide-details
          prepend-inner-icon="mdi-magnify"
          label="Search"
          class="hidden-sm-and-down"
        ></v-text-field>

      <v-spacer></v-spacer>


      <h2>Filter By Price</h2>
    <v-list shaped>
      <v-list-item-group
        v-model="model"
        multiple
      >
        <template v-for="(item, i) in items">
          <v-divider
            v-if="!item"
            :key="`divider-${i}`"
          ></v-divider>

          <v-list-item
            v-else
            :key="`item-${i}`"
            :value="item"
            active-class="deep-purple--text text--accent-4"
          >
            <template v-slot:default="{ active }">
              <v-list-item-content>
                <v-list-item-title v-text="item"></v-list-item-title>
              </v-list-item-content>

              <v-list-item-action>
                <v-checkbox
                  :input-value="active"
                  color="deep-purple accent-4"
                ></v-checkbox>
              </v-list-item-action>
            </template>
          </v-list-item>
        </template>
      </v-list-item-group>

    </v-list>
    <h2>Filter by Category</h2>
    <v-list>

      <v-list-item
        v-for="product in products"
        :key="product.title"
      >

        <v-list-item-content>
          <a href="#"><v-list-item-title v-text="product.title"></v-list-item-title></a>

        </v-list-item-content>

      </v-list-item>
    </v-list>
    <h2>Top Rated Products</h2>
    <v-row wrap justify-space-between>
          <v-col v-for="top in tops" :key="top.id" cols="8" md="4">
                        <v-img
                          class="white--text align-end"
                          height="100%"
                          :src="top.src"
                        >
                        </v-img>
           </v-col>

          <v-col v-for="top in tops" :key="top.id" cols="12" md="8">
                     <v-card-text class="text--primary">
                         <div>{{ top.name }}</div>


                          <div>{{ top.prize }}</div>
                      </v-card-text>
           </v-col>
      </v-row>
  </v-card>
      </v-col>

    <v-spacer></v-spacer>

      <v-col
        cols="12"
        md="7"

      >

        <v-row>
         <v-col v-for="categorie in categories" :key="categorie.id" cols="12" md="4">
           <v-hover>
              <template v-slot:default="{ hover }">
                <v-card outlined class="mx-auto">
                        <v-img
                          class="white--text align-end"
                          height="100%"
                          :src="categorie.src"
                        >
                        </v-img>
                            <v-card-subtitle class="pb-0">{{ categorie.prize }}</v-card-subtitle>
                              <v-card-text class="text--primary">
                                 <div>{{ categorie.name }}</div>
                                 <div>{{ categorie.category}}</div>
                              </v-card-text>

                              <v-fade-transition>
                            <v-overlay
                              v-if="hover"
                              absolute
                              color="#036358"
                            >
                            <v-card-actions>
                                  <v-btn icon><v-icon>mdi-cart</v-icon></v-btn>
                                  <v-btn icon><v-icon>mdi-eye</v-icon></v-btn>
                              </v-card-actions>
                            </v-overlay>
                          </v-fade-transition>
                      </v-card>
                </template>
              </v-hover>
           </v-col>
        </v-row>

      </v-col>

    </v-row>
  </v-container>

</template>

<script>
  export default {
    data: () => ({
        items: [
                '৳ 1 to 500',
                '৳ 500 to 1000',
                '৳ 1000 to 5000',
                '৳ 5000 to 10,000',
                '৳ 10,000 to 20,000',
               ],
      products: [
            {  title: 'Dress' },
            { title: 'show' },
            { title: 'new' },

          ],
      categories: [
          {
            id: 1,
            prize: "tk 1,000",
            name: "Top western road trips",
            category: "Three-pice",
            src: require("../assets/images/feature1.jpg")
          },
          {
            id: 2,
            prize: "tk 2,000",
            name: "Christmas tales to read",
            category: "Four-pice",
            src: require("../assets/images/feature7.jpg")
          },
          {
            id: 3,
            prize: "tk 3,000",
            name: "pakistani loan",
            category: "Four-pice",
            src: require("../assets/images/feature6.jpg")
          }
        ],
        tops: [
          {
            id: 1,
            name: "Top western road trips",
            category: "Three-pice",
            prize: "tk 1,000",
            src: require("../assets/images/feature1.jpg")
          },
        ]


    }),
  }
</script>

<style>
.box {
    width: 400px;
    background: grey;
    margin: 5px;
}
.text {
    width: 300px;
    margin: 10px;
}

h2 {
   margin: 10px;
}


</style>
