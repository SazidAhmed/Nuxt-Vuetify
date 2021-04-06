<template>
  <v-container>
      <!----details---->
      <v-row wrap justify-space-between>
        <v-col cols="auto" >
         <v-row wrap justify-space-between>
           <v-col cols="auto" >
              <v-col cols="12">
             <v-img
                          class="white--text align-end"
                          height="100%"
                          width="400"
                          :src="activePic"
                        >
                        </v-img>
              </v-col>
           </v-col>
             <v-col cols="auto" >
               <v-col cols="auto">
                 <v-col v-for="(picture, index) in pictures" :key="picture.name" cols="8" md="4">
                        <v-img
                          class="white--text align-end"
                          height="100%"
                          width="400"
                          :src="pictures" @mouseonover="changeActivePic(index)"
                          :class="{ active: indexOfActive ? true : false}">

                        </v-img>
                </v-col>
             </v-col>
          </v-col>
       </v-row>
        </v-col>
        <v-col cols="auto">
           <div>
               <h2>afrin</h2>
               <p>৳ 1495</p>
           </div>
           <div>STOCK : </div>
           <div>CATEGORY : Dress</div>
           <div>TAGS: T-shirt</div>
           <div>SHARE : </div>

           <v-btn class="mt-5" rounded color="grey darken-1"><NuxtLink to="/shoppingCart" style="text-decoration: none; color: inherit;">Add To Cart</NuxtLink></v-btn>
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

 <v-container
    fluid

  >
    <v-row
    >
      <v-col cols="12">
        <v-btn @click="show = !show">
          toggle
        </v-btn>
      </v-col>


        <v-tooltip
          v-model="show"
          top
        >


      <div class="mt-10" width="400px">
       <span>Programmatic tooltip</span>
        <v-textarea
          filled
          name="input-7-4"
          label="Filled textarea"
          value="The Woodman set to work at once, and so sharp was his axe that the tree was soon chopped nearly through."
        ></v-textarea>
      </div>

        </v-tooltip>


    </v-row>
  </v-container>
  <!---checkbox---->
  <v-checkbox
      v-model="v0"
      label="Visible"
    ></v-checkbox>
    <v-banner
      v-model="v0"
      single-line
      transition="slide-y-transition"
    >
      <div class="mt-10" width="250px" >
       <span>Programmatic tooltip</span>
        <v-textarea
          filled
          name="input-7-4"
          label="Filled textarea"
          value="The Woodman set to work at once, and so sharp was his axe that the tree was soon chopped nearly through."
        ></v-textarea>
      </div>
    </v-banner>
  </v-container>
</template>

<script>
export default {
 data() {
    return {
      v0: false,
      show: false,
      indexOfActive: 0,
      activePic: 'https://i.pinimg.com/originals/cc/ab/e5/ccabe55eba2e9419388c946addaa9f2d.jpg',
      pictures: [
          'https://stylesatlife.com/wp-content/uploads/2019/07/15-Attractive-2-Years-Girl-Dress-Designs-for-Birthday.jpg',
          'https://stylesatlife.com/wp-content/uploads/2019/07/Top-15-Cute-4-Years-Girl-Dress-Designs-for-Occasion.jpg',
          'https://stylesatlife.com/wp-content/uploads/2020/01/15-Beautiful-and-Best-14-Years-Old-Girl-Dress-Designs.jpg',
      ]
    }
 },
 methods: {
   changeActivePic(index) {
     this.activePic = this.pictures[index];
   }
 }
};
</script>
<style>
  h3 {
    font-size: 25px;
}
</style>
