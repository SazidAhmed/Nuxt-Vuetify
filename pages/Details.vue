
<template>
  <v-container>
      <!----details---->
      <v-row wrap justify-space-between>
        <v-col cols="auto" >
         <v-row wrap justify-space-between>
           <v-col cols="auto" >
             <v-img width="400" class="mt-5" src="../assets/images/feature1.jpg"></v-img>
           </v-col>
             <v-col cols="auto" >
               <v-col cols="auto">
                 <v-col v-for="top in tops" :key="top.id" cols="8" md="4">
                        <v-img
                          class="white--text align-end"
                          height="100%"
                          width="400"
                          :src="top.src"
                        >
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

           <v-btn>Add To Cart</v-btn>
        </v-col>
      </v-row>
      </v-container>
</template>

<script>
export default {
  name: "Login",
  data: () => ({

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

  }),


};
</script>
