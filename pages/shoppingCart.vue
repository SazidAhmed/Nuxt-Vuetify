<template>
  <v-app id="inspire">

    <v-container fluid>
        <h2>Shopping card</h2>
      <v-simple-table dense>
            <thead>
              <tr>
                <th>images</th>
                <th>Product</th>
                <th>Price</th>
                <th>Quantity</th>
                <th>Total</th>
                <th>remove</th>
              </tr>
            </thead>
            <tbody class="pt-5">
            <!-- Cart items-->
              <tr>
                  <td class="mx-5">
                    <a href="#"><img src="https://assets.myntassets.com/dpr_1.5,q_60,w_400,c_limit,fl_progressive/assets/images/11840386/2020/5/8/fff46b5f-5057-47bb-96ec-3597dcf71a821588918409828-Wish-Karo-Baby-Girls-Satin-Frock-Dress-7701588918409121-1.jpg" alt="" height="100px"></a>
                  </td>
                  <td class="product-name">
                    <a href="#">afrin </a>
                  </td>
                  <td class="product-price-cart">
                    <span class="amount">৳ 1495</span>
                  </td>
                  <td class="product-quantity">
                    <form id="cartUpdateForm0" action="http://127.0.0.1:8000/products/1" method="POST"><input type="hidden" name="_token" value="QA6PjxeToeGdzZ2sW34n3miz7KBRsaAyDbiazPFa">
                        <input id="qty0" name="qty" value="1" type="number">
                    </form>
                  </td>
                  <td class="product-subtotal">
                      ৳ 1495
                  </td>
                  <td class="product-remove">
                      <form action="http://127.0.0.1:8000/product/1" method="POST">
                            <input type="hidden" name="_token" value="QA6PjxeToeGdzZ2sW34n3miz7KBRsaAyDbiazPFa">                                  <button class="btn btn-link" title="Remove Item"><i class="pe-7s-close"></i></button>
                      </form>
                  </td>
             </tr>
           </tbody>
      </v-simple-table>
   </v-container>
          <div class="row">
            <div class="col-md-5 ml-auto">
              <v-simple-table class="text-left">
                  <template v-slot:default>
                    <tbody>
                      <tr
                        v-for="item in items"
                        :key="item.id"
                      >
                        <td>{{ item.name }}</td>
                        <td>{{ item.prize }}</td>
                      </tr>
                    </tbody>
                  </template>
              </v-simple-table>
              <v-btn rounded color="primary" dark class="mt-5">
                 <NuxtLink to="/checkOut" style="text-decoration: none; color: inherit;">Checkout</NuxtLink>
              </v-btn>
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
             message4: '1',
             quantity: 1,

            items: [
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
