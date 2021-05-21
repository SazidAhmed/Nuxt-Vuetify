<template>
    <v-app >
       <v-container>
         <!---first row for shopping Cart--->

    <v-row>
      <v-col
        cols="12"
        md="6"
      >
      <h2>Shopping Cart</h2>
      <!---2nd row for shopping cart---->
     <v-main class="mb-10 pt-5">
      <v-row>
      <v-col
        cols="auto"
        md="4"
      >
        <v-img

          height="100"
          max-width="100"
          src="https://picsum.photos/id/11/500/300"
        ></v-img>
      </v-col>



      <v-col md="6">
        <h3> Modern Dreeses</h3>
        <v-spacer></v-spacer>
        <span>Qty</span>

      </v-col>

      <v-col md="2">
        <v-icon>mdi-window-close</v-icon>
        <v-spacer></v-spacer>
        <span>208S</span>

      </v-col>

    </v-row>

</v-main>
<v-divider ></v-divider>
<div class="text-center pt-5">
    <v-btn
      class="ma-2"
      outlined
      width="250"
    >
      Continue Shopping
    </v-btn>
       <v-btn
      class="ma-2"
      outlined
      width="250"
    >
      Update Cart
    </v-btn>
  </div>
  <!---From--->
<v-row justify="center">
    <v-col
      cols="12"
      sm="10"
      md="8"
      lg="10"
    >
      <div ref="form">
        <v-card-text>
          <v-row>
        <v-col
          cols="12"
          sm="6"
        >

         <v-text-field
            ref="name"
            v-model="name"
            :rules="[() => !!name || 'This field is required']"
            :error-messages="errorMessages"
            label="First Name"
            placeholder="John Doe"
            required
            solo-inverted
          ></v-text-field>
        </v-col>

        <v-col
          cols="12"
          sm="6"
        >
          <v-text-field
            ref="name"
            v-model="name"
            :rules="[() => !!name || 'This field is required']"
            :error-messages="errorMessages"
            label="Last Name"
            placeholder="John Doe"
            required
            solo-inverted
          ></v-text-field>
        </v-col>
      </v-row>
          <v-text-field
            ref="name"
            v-model="name"
            :rules="[() => !!name || 'This field is required']"
            :error-messages="errorMessages"
            label="Company Name"
            required
          ></v-text-field>
          <v-text-field
            ref="address"
            v-model="address"
            :rules="[
              () => !!address || 'This field is required',
              () => !!address && address.length <= 25 || 'Address must be less than 25 characters',
              addressCheck
            ]"
            label="Address"
            placeholder="Snowy Rock Pl"
            counter="25"
            required
          ></v-text-field>
          <v-text-field
            ref="city"
            v-model="city"
            :rules="[() => !!city || 'This field is required', addressCheck]"
            label="City"
            placeholder="El Paso"
            required
          ></v-text-field>
          <v-text-field
            ref="state"
            v-model="state"
            :rules="[() => !!state || 'This field is required']"
            label="State/Province/Region"
            required
            placeholder="TX"
          ></v-text-field>
          <v-text-field
            ref="zip"
            v-model="zip"
            :rules="[() => !!zip || 'This field is required']"
            label="ZIP / Postal Code"
            required
            placeholder="79938"
          ></v-text-field>
          <v-autocomplete
            ref="country"
            v-model="country"
            :rules="[() => !!country || 'This field is required']"
            :items="countries"
            label="Country"
            placeholder="Select..."
            required
          ></v-autocomplete>
        </v-card-text>
        <v-divider class="mt-12"></v-divider>
        <v-card-actions>
          <v-btn text>
            Cancel
          </v-btn>
          <v-spacer></v-spacer>
          <v-slide-x-reverse-transition>
            <v-tooltip
              v-if="formHasErrors"
              left
            >
              <template v-slot:activator="{ on, attrs }">
                <v-btn
                  icon
                  class="my-0"
                  v-bind="attrs"
                  @click="resetForm"
                  v-on="on"
                >
                  <v-icon>mdi-refresh</v-icon>
                </v-btn>
              </template>
              <span>Refresh form</span>
            </v-tooltip>
          </v-slide-x-reverse-transition>
          <v-btn
            color="primary"
            text
            @click="submit"
          >
            Submit
          </v-btn>
        </v-card-actions>
      </div>
    </v-col>
  </v-row>

     </v-col>

       <!---2nd row for shopping cart---->
      <v-col
        cols="6"
        md="4"
      >
        <h2>Cart Totals</h2>
        <!---First Cart--->
        <v-card outlined>
        <div class="ma-4">
          <v-icon>mdi-heart</v-icon>
          <small>Add Cupon</small>
        </div>
        <div class="ma-2">
         <v-select
          :items="items"
          filled
          label="Filled style"
          dense
        ></v-select>
        </div>
        <div class="text-center ma-2">
        <v-btn block  color="black white--text">
    Block Button
  </v-btn>
        </div>
        </v-card>
        <!---First Cart--->
        <!---Second Cart--->
                <v-card outlined>
        <v-card-actions class="justify-space-between">
      <v-btn text>
        Sub Totals
      </v-btn>
      <v-btn
        color="primary"
        text
      >
       320.0
      </v-btn>
    </v-card-actions>
    <v-divider></v-divider>
     <v-container fluid>
    <p>Shipping</p>

    <v-radio-group
      v-model="radios"
      mandatory
    >
    <v-card-actions class="justify-space-between">
      <v-radio
        label="Standard"
        value="Standard"
      ></v-radio>
       <v-btn
        color="primary"
        text
      >
       120.0
      </v-btn>
      </v-card-actions>
      <v-card-actions class="justify-space-between">
      <v-radio
        label="Express"
        value="Express"
      ></v-radio>
       <v-btn
        color="primary"
        text
      >
       100.0
      </v-btn>
      </v-card-actions>
    </v-radio-group>

    <p>Shipping to CA, Bangladesh</p>
    <v-select
          :items="teams"
          label="Standard"
        ></v-select>
  </v-container>
    <v-card-actions class="justify-space-between">
      <v-btn text>
        Totals
      </v-btn>
      <v-btn
        color="primary"
        text
      >
       540.0
      </v-btn>
    </v-card-actions>
        <div class="text-center ">
        <v-btn block  color="black white--text">
    Proceed To Checkout
  </v-btn>
        </div>
        </v-card>
        <!---Second Cart--->

      </v-col>
    </v-row>

    <!---first row---->
  </v-container>
  </v-app>
</template>
<script>
  export default {
    data: () => ({
      items: ['A', 'B', 'C', 'D'],
      teams: ['Bangladesh', 'America', 'Chaina', 'Malyasia'],
       radios: null,
    }),
  }
</script>

