<template>
  <v-app id="inspire">

    <v-container fluid>
        <h2>Shopping card</h2>
      <v-simple-table dense>
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left">
            IMAGES
          </th>
          <th class="text-left">
            PRODUCT
          </th>
          <th class="text-left">
            PRICE
          </th>
          <th class="text-left">
            QUANTITY
          </th>
          <th class="text-left">
            TOTAL
          </th>
          <th class="text-left">
            REMOVE
          </th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="item in items"
          :key="item.id"
        >
          <td>{{ item.image }}</td>
          <td>{{ item.product }}</td>
          <td>{{ item.prize }}</td>
          <td>{{ item.quantity }}</td>
          <td>{{ item.total }}</td>
          <td>{{ item.remove }}</td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
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
                    :key="item.desert"
                  >
                    <td>{{ item.name }}</td>
                    <td>{{ item.prize }}</td>
                  </tr>
                </tbody>
              </template>
          </v-simple-table>
          </v-card>
          <v-btn class="mt-5"><NuxtLink to="/checkOut" style="text-decoration: none; color: inherit;">Proceed to checkout</NuxtLink></v-btn>
         </div>
      </div>
    </v-app>
</template>

<script>
export default {
   data () {
        return {
            name:'',
            loading: false,
  items: [
          {
            image: '',
            product: 'afrin',
            prize: 1549,
            quantity: 100,
            total: 1549,
            remove: 0,

          },
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

            valid: true,
            titleRules: [],
        }
    },

};
</script>
