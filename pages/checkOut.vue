<template>
  <v-container>

      <v-row no-gutters>
      <v-col
        cols="12"
        sm="6"
        md="6"
      >

      <!---colum1---->

    <v-card-title class="headline ">
        CUSTOMER DETAILS
    </v-card-title>
    <v-divider></v-divider>
     <v-form v-model="valid">
    <v-container>
      <v-row>
        <v-col
          cols="12"
          md="12"
        >
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

        <v-col
          cols="12"
          md="12"
        >
        <v-text-field
          v-model="phoneNumber"
          :counter="7"
          label="Phone Number"
          required
        ></v-text-field>
        </v-col>

        <v-col
          cols="12"
          md="12"
        >
          <v-text-field
            v-model="email"
            :rules="emailRules"
            label="Enter Your E-mail Address"
            dense
            filled
            rounded
            required
          ></v-text-field>
        </v-col>
        <h3>
            <label class="home">Any Special Note For Delivery?</label>
             <input id="ship-box" type="checkbox" />
        </h3>
      </v-row>
    </v-container>
  </v-form>


      </v-col>

  <v-col
        cols="6"
        md="6"
      >
        <v-card
          class="pa-2"
          outlined
          tile
        >
        <v-card-title class="headline red lighten-3">
              YOUR ORDER
        </v-card-title>
       <v-simple-table
    fixed-header
  >
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left">
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
          <td>{{ item.Product }}</td>
          <td>{{ item.Total }}</td>
        </tr>
      </tbody>
       <div class="heading">
             <h5 class="title">Cash On Dalivery</h5>
                  </div>
                     <div id="payment">
                        <div class="body">
                             <p>Payment method for this order is "Cash On Delivery".</p>
                             <p>Please Check Your Name, Phone Number, Delivery Address and then place order .</p>
                         </div>
                      </div>
    </template>
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
