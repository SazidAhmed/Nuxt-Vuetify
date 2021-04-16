<template>
<v-app id="inspire">
  <div class="cart-main-area pt-95 pb-100">
    <v-container fluid>
        <div class="row">
            <div class="col-lg-12 col-md-12 col-sm-12 col-xs-12">
                  <h1 class="cart-heading">Shopping Cart</h1>
                  <div class="table-content table-responsive">
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
                                  <td class="mt-5">
                                      <a href="#"><img src="http://127.0.0.1:8000/imgfiles/proImg/afrin1614181357.jpg" alt="" height="100px"></a>
                                  </td>
                                  <td class="product-name"><a href="#">afrin </a></td>
                                  <td class="product-price-cart"><span class="amount">৳ 1495</span></td>
                                  <td class="product-quantity">
                                    <form id="cartUpdateForm0" action="http://127.0.0.1:8000/products/1" method="POST"><input type="hidden" name="_token" value="QA6PjxeToeGdzZ2sW34n3miz7KBRsaAyDbiazPFa">
                                    <input id="qty0" name="qty" value="1" type="number">

                                    </form>
                                  </td>
                                  <td class="product-subtotal">৳ 1495
                                  </td>
                                  <td class="product-remove">
                                    <form action="http://127.0.0.1:8000/product/1" method="POST"><input type="hidden" name="_token" value="QA6PjxeToeGdzZ2sW34n3miz7KBRsaAyDbiazPFa">                                  <button class="btn btn-link" title="Remove Item"><i class="pe-7s-close"></i></button>
                                    </form>
                                  </td>
                              </tr>
                                                      </tbody>
                      </v-simple-table>
                  </div>

                  <div class="row">
                    <div class="col-md-5 ml-auto">
                        <div class="cart-page-total">
                            <h2>Cart totals</h2>
                            <ul>
                                <li>Subtotal<span>৳ 1495</span></li>
                                <li>Discount<span>৳ 0</span></li>
                                <li>Total Payment<span>৳ 1495</span></li>
                            </ul>
                            <a href="http://127.0.0.1:8000/checkout/1495">Proceed to checkout</a>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </v-container>
  </div>

</v-app>
</template>

<script>
export default {

}
</script>

<style>

</style>
