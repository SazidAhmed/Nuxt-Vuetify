<template>
  <v-app>
    <v-container class="pt-10">
      <v-layout row wrap >
         <v-flex
          sm6
          xs12
          md6
          lg3
      >
       <v-card class="ma-3">
    <v-list-item  >
       <v-list-item-avatar
        tile
        class="mt-n7"
      >
      <v-sheet color="green" width="80" height="80" elevation="10">
            <v-icon dark large >mdi-account-key</v-icon>
      </v-sheet>
      </v-list-item-avatar>
      <v-list-item-content>
        <div class="overline text-right">1</div>
        <v-list-item-title class="headline mb-1 text-right" >Admins</v-list-item-title>

      </v-list-item-content>
    </v-list-item>
  </v-card>
      </v-flex>
       <v-flex
        sm6
        xs12
        md6
        lg3
      >
       <v-card class="ma-3">
    <v-list-item>
       <v-list-item-avatar
        tile
        class="mt-n7"
      >
      <v-sheet color="#F44336" width="80" height="80" elevation="10">
            <v-icon dark large>mdi-account-multiple</v-icon>
      </v-sheet>
      </v-list-item-avatar>
      <v-list-item-content>
        <div class="overline text-right">1</div>
        <v-list-item-title class="headline mb-1 text-right" >Customers</v-list-item-title>

      </v-list-item-content>
    </v-list-item>
  </v-card>
      </v-flex>
       <v-flex
        sm6
        xs12
        md6
        lg3
      >
       <v-card class="ma-3">
    <v-list-item>
       <v-list-item-avatar
        tile
        class="mt-n7"
      >
      <v-sheet color="#03A9F4" width="80" height="80" elevation="10">
            <v-icon dark large>mdi-dna</v-icon>
      </v-sheet>
      </v-list-item-avatar>
      <v-list-item-content>
        <div class="overline text-right">1</div>
        <v-list-item-title class="headline mb-1 text-right" >Categories</v-list-item-title>

      </v-list-item-content>
    </v-list-item>
  </v-card>
      </v-flex>
       <v-flex
        sm6
        xs12
        md6
        lg3
      >
       <v-card class="ma-3">
    <v-list-item >
       <v-list-item-avatar
        tile
        class="mt-n7"
      >
      <v-sheet color="#FFC107" width="80" height="80" elevation="10">
            <v-icon dark large>mdi-account-tie</v-icon>
      </v-sheet>
      </v-list-item-avatar>
      <v-list-item-content>
        <div class="overline text-right">1</div>
        <v-list-item-title class="headline mb-1 text-right" >Products</v-list-item-title>

      </v-list-item-content>
    </v-list-item>
  </v-card>
      </v-flex>
        <v-row dense class="pt-10">
                <v-col
                v-for="(team, i) in teams"
                :key="i"
                cols="sm12 md6 lg3 xl3"

                >
                <v-card
                    :color="team.color"
                    dark
                    class="ma-3"
                    height="200"
                >
                    <v-row wrap>


            <div class="d-flex">
                        <v-btn icon class="ma-6">
                            <v-icon large v-text="team.icon"></v-icon>
                        </v-btn>
                        <v-card-text>
                            <h2 class="card-title ma-4">New Orders</h2>
                        </v-card-text>
              </div>
              </v-row>
              <v-row >
                  <v-col >
                    <v-card-actions class="pt-0">
                        <h2 class="font-light text-white text-center">0</h2>
                    </v-card-actions>
                  </v-col>
                <v-spacer></v-spacer>
              </v-row>



                </v-card>
                </v-col>
            </v-row>
            <!-- Cards Ends-->
             <!-- Members Data Table-->
             <v-container class="pt-10">
              <v-card width="100%">

                <v-card-title>
                    <h2 class="grey--text">Member's Orders</h2>
                </v-card-title>
                <v-data-table :headers="headers" :items="desserts" :search="search" >
                    <template v-slot:[`item.image`] ="{ item }">
                        <img :src="'assets/img/' + item.image" style="width: 60px; margin-top: 5px;" />
                        </template>
                        <template v-slot:[`item.actions`]="{ item }" >
                        <v-icon small color="cyan" class="mr-2" @click="editItem(item)"> mdi-eye </v-icon>
                        <v-icon small color="red"  @click="deleteItem(item)"> mdi-pencil</v-icon>
                    </template>
                </v-data-table>
              </v-card>
             </v-container>
           <!-- End datatable -->
           <!-- Guest order Table-->
             <v-container class="pt-10">
              <v-card width="100%">

                <v-card-title>
                    <h2 class="grey--text">Guest Orders</h2>
                </v-card-title>
                <v-data-table :headers="headers" :items="products" :search="search" >
                    <template v-slot:[`item.image`] ="{ item }">
                        <img :src="'assets/img/' + item.image" style="width: 60px; margin-top: 5px;" />
                        </template>
                        <template v-slot:[`item.actions`]="{ item }" >
                        <v-icon small color="cyan" class="mr-2" @click="editItem(item)"> mdi-eye </v-icon>
                        <v-icon small color="red"  @click="deleteItem(item)"> mdi-pencil </v-icon>
                    </template>
                </v-data-table>
              </v-card>
             </v-container>
           <!-- End table -->

      </v-layout>
    </v-container>
  </v-app>
</template>

<script>
// @ is an alias to /src


export default {
  name: 'team',
  components: {

  },

    data () {
        return {
            search: '',
            createDialog:false,
            deleteDialog: false,
            headers: [
                { text: 'Index', align: 'start', sortable: true, value: 'id'},
                { text: 'Date', align: 'start', sortable: true, value: 'created_at'},
                { text: 'status', align: 'start', sortable: false, value: 'status'},
                { text: 'Name', align: 'start', sortable: true, value: 'name'},
                { text: 'Mobile', align: 'start', sortable: true, value: 'mobile'},
                { text: 'Address', align: 'start', sortable: true, value: 'address'},
                { text: 'Actions', value: 'actions', sortable: false },
              ],
              desserts: [
                {
                    id: 1,
                    created_at: '15-01-2021',
                    status: 'On-Delivery',
                    name: 'organic',
                    mobile: '01820051200',
                    address: 'uttara',
                },

            ],
            products: [
                {
                    id: 1,
                    created_at: '15-01-2021',
                    status: 'On-Delivery',
                    name: 'organic',
                    mobile: '01820051200',
                    address: 'uttara',
                },

            ],
         teams: [
                {
                    color: 'deep-purple accent-2',
                    icon: 'mdi-cart',

                },
                {
                    color: 'cyan',
                    icon: 'mdi-check-circle',

                },
                {
                    color: 'light-blue',
                    icon: 'mdi-truck-delivery',

                },

            ],

       }
    },
     methods:{
            createItem() {
                this.createDialog = true;
            },
            editItem (item) {
                this.createDialog = true;
                console.log(item.id);
                console.log(item.name);
            },

            deleteItem (item) {
                this.deleteDialog = true;
                console.log(item.id);
                console.log(item.name);
            },
        }
}
</script>
