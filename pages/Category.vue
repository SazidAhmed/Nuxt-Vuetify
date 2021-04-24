<template>
    <v-app >
        <v-container class="pt-10">
            <!-- Data Table-->
            <v-card color="brown lighten-2">
              <v-card-title>Product Categories</v-card-title>
              <v-row>
                <v-col>

                </v-col>
                <v-col>
                  <v-card-title>
                      <v-text-field v-model="search" append-icon="mdi-magnify" label="Search" single-line hide-details ></v-text-field>
                          <v-btn medium @click="createItem()" color="green" dark class="ma-2" right>
                              <v-icon dark medium> mdi-plus </v-icon>
                              Add New
                          </v-btn>
                  </v-card-title>
                </v-col>
              </v-row>
                <!-- datatable -->
                <v-data-table :headers="headers" :items="desserts" :search="search" dark>
                    <template v-slot:[`item.image`] ="{ item } ">
                        <img :src="'assets/img/' + item.image" style="width: 60px; margin-top: 5px;" />
                    </template>
                    <template v-slot:[`item.actions`]="{ item }" >
                          <v-icon small color="cyan" class="mr-2" @click="editItem(item)">
                             mdi-eye
                          </v-icon>
                          <v-icon small color="cyan" class="mr-2" @click="editItem(item)">
                             mdi-pencil
                          </v-icon>
                          <v-icon small color="red"  @click="deleteItem(item)">
                             mdi-delete
                          </v-icon>
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
                <v-card>
                  <v-card-title class="headline">Confirm To Delete.</v-card-title>
                    <v-card-text class=" text-h6 text-center"></v-card-text>
                      <v-card-actions >
                          <v-spacer></v-spacer>
                          <v-btn
                          color="red darken-1"
                          text
                          @click="deleteDialog = false"
                          >
                          Cancel
                          </v-btn>
                          <v-btn
                          color="green darken-1"
                          text
                          @click="deleteDialog = false"
                          >
                          Confirm
                          </v-btn>
                      </v-card-actions>
                </v-card>
            </v-dialog>
            </v-row>

            <!-- Create Modal -->

            <v-row justify="center">
              <v-dialog
                    v-model="createDialog"
                    persistent
                    max-width="600px"
                >
                 <v-card>
                    <v-card-title>
                        <span class="headline">New Category</span>
                    </v-card-title>
                    <v-card-text>
                        <v-container>
                          <v-row>
                            <v-col
                              cols="12"
                              sm="12"
                              md="7"
                              >
                                <v-text-field
                                    label="title"
                                    hint="Enter Name Of Title Here"
                                ></v-text-field>
                                <v-text-field
                                    label="tagline"
                                    hint="Enter Name Of TagLine Here"
                                ></v-text-field>
                                <v-text-field
                                    label="displaysection"
                                    hint="Enter Name Of displaysection Here"
                                ></v-text-field>
                            </v-col>
                            <v-col cols="12" sm="12" md="5" >
                              <v-file-input  accept="image/*" label="Upload Image" ></v-file-input>
                          </v-col>
                          </v-row>
                        </v-container>
                    </v-card-text>
                    <v-card-actions>
                        <v-spacer></v-spacer>
                        <v-btn
                        color="red darken-1"
                        text
                        @click="createDialog = false"
                        >
                        Cancel
                        </v-btn>
                        <v-btn
                        color="green darken-1"
                        text
                        @click="createDialog = false"
                        >
                        Submit
                        </v-btn>
                    </v-card-actions>
                  </v-card>
              </v-dialog>
            </v-row>
      </v-container>
  </v-app>
</template>

<script>
    export default {
        data () {
        return {
            search: '',
            createDialog:false,
            deleteDialog: false,
            headers: [
                { text: 'Index', align: 'start', sortable: true, value: 'id'},
                { text: 'Image', align: 'start', sortable: false, value: 'image'},
                { text: 'Name', align: 'start', sortable: true, value: 'name'},
                { text: 'Actions', value: 'actions', sortable: false },
            ],
            desserts: [
                {
                    id: 1,
                    image: 'require("../assets/images/box3.png")',
                    name: 'Afrin',
                },
                {
                    id: 2,
                    image: 'require("../assets/images/box3.png")',
                    name: 'Sarker',
                },
                {
                    id: 3,
                    image: 'require("../assets/images/box3.png")',
                    name: 'Nupor',
                },
                {
                    id: 4,
                    image: 'require("../assets/images/box3.png")',
                    name: 'Pomi',
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
