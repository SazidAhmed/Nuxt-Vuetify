<template>
  <v-app id="inspire">

    <v-container fluid>
            <h2>Shopping card</h2>
            <!-- Data Table-->
            <v-card>

                <!-- datatable -->
                <v-data-table class="elevation-1" :headers="headers" :items="category" :loading="loading"
                    loading-text="Loading... Please wait" :footer-props="{itemsPerPageOptions: [5,10,15],itemsPerPageText: 'Data Per Page','show-current-page': true,'show-first-last-page': true}">
                    <template v-slot:[`item.actions`]="{ item }" >
                        <v-icon small color="red"  @click="deleteBtn(item.id)"> mdi-delete </v-icon>
                    </template>
                </v-data-table>
                <!-- End datatable -->
            </v-card>

            <!-- Delete Modal -->
            <v-row justify="center">
                <v-dialog
                    v-model="deleteDialog"
                    persistent
                    max-width="290"
                >
                <form @submit.prevent="deleteData()" enctype="multipart/form-data">
                        <v-card>
                            <v-card-title>
                                <span class="headline">Warning!!!</span>
                            </v-card-title>
                            <v-card-text>
                                <v-container>
                                <v-row>
                                    <h3>Are You Sure???</h3>
                                </v-row>
                                </v-container>
                            </v-card-text>
                            <v-card-actions>
                                <v-spacer></v-spacer>
                                <v-btn color="red darken-1" text @click="deleteDialog = false">No</v-btn>
                                <v-btn type="submit" color="green darken-1" text>Yes</v-btn>
                            </v-card-actions>
                        </v-card>
                    </form>
                </v-dialog>
            </v-row>

      </v-container>
      <div class="row">
        <div class="col-md-5 ml-auto mt-10">
            <h2>Cart totals</h2>
          <v-card max-width="450" >
          <v-simple-table dark >
              <template v-slot:default>
                <tbody>
                  <tr
                    v-for="item in desserts"
                    :key="item.id"
                  >
                    <td>{{ item.name }}</td>
                    <td>{{ item.prize }}</td>
                  </tr>
                </tbody>
              </template>
          </v-simple-table>
          </v-card>
          <v-btn class="mt-5">Proceed to checkout</v-btn>
         </div>
      </div>
    </v-app>
</template>

<script>
export default {
   data () {
        return {
            name:'',
            color:'',
            loading: false,
            text: '',
            deleteDialog: false,
            headers: [
                { text: 'IMAGES', align: 'start', sortable: true, value: 'image'},
                { text: 'PRODUCT', align: 'start', sortable: false, value: 'product'},
                { text: 'PRIZE', align: 'start', sortable: false, value: 'prize'},
                { text: 'QUANTITY', align: 'start', sortable: false, value: 'quantity'},
                { text: 'TOTAL', align: 'start', sortable: false, value: 'total'},
                { text: 'REMOVE', value: 'actions', sortable: false },
            ],
            desserts: [
                        {
                          name: 'Subtotal',
                          prize:  4000,
                        },
                        {
                          name: 'Discount',
                          prize: 100
                        },
                        {
                          name: 'Total Payment',
                          prize: 3900
                        },

            ],
            category: [],
            actionData:[],
            valid: true,
            titleRules: [],
        }
    },

    mounted() {
        this.getCategory();

    },

    methods:{

        getCategory(){
            fetch('http://localhost:3000/category')
            .then(res => res.json())
            .then((data) => {
                console.log(data)
                this.category = data;
                this.loading = false;
            })

        },
        deleteBtn(id) {
            fetch('http://localhost:3000/category/' + id )
            .then(res => res.json())
            .then((data) => {
                this.actionData = data;
                console.log('delete data:',this.actionData);
                this.deleteDialog = true;
            })

        },
        deleteData(){
            this.loading = true;
            fetch('http://localhost:3000/category/' + this.actionData.id, { method: 'DELETE' })
                .then(() => {
                    this.color = 'green';
                    this.snackbar = true;
                    this.text = "Record Deleted Successfully!";
                    this.category = this.category.filter(category => {
                        return category.id !== this.actionData.id
                    })
                    this.deleteDialog = false;
                    this.loading = false;
                })

        }
    }

};
</script>
