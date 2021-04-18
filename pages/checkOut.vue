<template>
  <v-container class="mt-5 pa-10">
    <v-row no-gutters >
      <v-col cols="12" sm="6" md="6">
        <!---colum1---->
        <v-card width="520" height="650" flat>
          <v-card-title class="headline ">
              CUSTOMER DETAILS
          </v-card-title>
          <v-divider></v-divider>
            <v-form v-model="valid">
                <v-container>
                  <v-row>
                      <v-col cols="12" md="12">
                         <v-text-field
                            v-model="firstname"
                            :rules="nameRules"
                            dense
                            filled
                            rounded
                            :counter="10"
                            label="Enter Your Full name"
                            required
                          ></v-text-field>
                      </v-col>
                      <v-col cols="12" md="12" >
                          <v-text-field
                              v-model="phoneNumber"
                              :counter="7"
                              label="Phone Number"
                              required
                              filled
                          ></v-text-field>
                      </v-col>
                    <v-col cols="12" md="12">
                        <v-text-field
                            v-model="email"
                            :rules="emailRules"
                            label="Enter Your E-mail Address"
                            dense
                            filled
                            rounded
                            required
                        ></v-text-field>
                          <v-checkbox v-model="v0">
                              <template v-slot:label>
                                <h3>
                                  ANY SPECIAL NOTES FOR DELIVERY?
                                </h3>
                              </template>
                          </v-checkbox>
                            <v-banner
                                v-model="v0"
                                single-line
                                transition="slide-y-transition">
                                <v-col cols="12" md="12">
                                  <div class="pb-5">Order Notes</div>
                                    <v-textarea
                                          dense
                                          filled
                                          required
                                          name="input-7-4"
                                          value="Notes about your order, e.g. spacial notes for delivery.">
                                    </v-textarea>
                                </v-col>
                            </v-banner>
                     </v-col>
                  </v-row>
                </v-container>
            </v-form>
        </v-card>
      </v-col>
     <v-col cols="12" md="6">
        <v-card class="pa-2 grey lighten-3" outlined tile height="650" width="500">
            <v-card-title class="headline grey lighten-2">
                YOUR ORDER
            </v-card-title>
              <v-divider></v-divider>
              <v-simple-table class="grey lighten-3">
                    <thead>
                      <tr>
                        <th class="text-center">
                           PRODUCT
                        </th>
                        <th class="text-left">
                           TOTAL
                        </th>
                      </tr>
                    </thead>
                    <tbody>
                        <tr
                          v-for="item in products"
                          :key="item.Product"
                        >
                          <td class="text-center">{{ item.Product }}</td>
                          <td>{{ item.Total }}</td>
                        </tr>
                    </tbody>
                        <v-card-text>
                            <div  class="display-1 text--primary mb-5">Cash On Dalivery</div>
                              <p class="mb-5">
                                  Payment method for this order is "Cash On Delivery"
                              </p>
                            <p class="mb-5">
                              Please Check Your Name, Phone Number, Delivery Address and then place order.
                            </p>
                          </v-card-text>
                              <v-card-actions>
                                  <v-btn class="primary">PLACE ORDER</v-btn>
                              </v-card-actions>
               </v-simple-table>
        </v-card>
      </v-col>
    </v-row>
<!-- checkout-area end -->
 </v-container>
</template>

<script>
  export default {
    data: () => ({
      valid: false,
      firstname: '',
      phoneNumber: '',
      nameRules: [
        v => !!v || 'Name is required',
        v => v.length <= 10 || 'Name must be less than 10 characters',
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid',
      ],
      v0: false,
      products: [
          {
            Product: 'afrin × 1',
            Total: 159,
          },
          {
            Product: 'CART SUBTOTAL',
            Total: 237,
          },
          {
            Product: 'TOTAL PAYMENT',
            Total: 2620,
          },

        ],
    }),
methods: {
      submit () {
        this.$refs.observer.validate()
      },
      clear () {
        this.name = ''
        this.phoneNumber = ''
        this.email = ''
        this.select = null
        this.checkbox = null
        this.$refs.observer.reset()
      },
    },
  }
</script>
<style>
label.home {
    font-size: 25px;
    margin: 10px;
}
</style>
