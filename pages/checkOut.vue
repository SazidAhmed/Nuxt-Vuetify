<template>
  <v-container>
    <div class="container">
        <div class="row">
            <div class="col-md-12">
                <div class="coupon-accordion">



                </div>
            </div>
        </div>
                <div class="row">
            <div class="col-lg-6 col-md-12 col-12">
                          <div class="checkbox-form">
                    <h3>customer Details</h3>
                    <div class="row">
                        <div class="col-md-12">
                            <div class="checkout-form-list">
                                <label>Full Name</label>
                                <input type="text" name="name" placeholder="Enter Your Name" required/>
                            </div>
                        </div>
                        <div class="col-md-12">
                            <div class="checkout-form-list">
                                <label>Phone</label>
                                <input type="number" name="phone" placeholder="Enter Your Phone Number" required/>
                            </div>
                        </div>
                        <div class="col-md-12">
                            <div class="checkout-form-list">
                                <label>Delivery Address</label>
                                <input type="text" name="address"  placeholder="Enter Your Address" required/>
                            </div>
                        </div>
                    </div>
                    <div class="different-address">
                        <div class="ship-different-title">
                            <h3>
                                <label>Any Special Note For Delivery?</label>
                                <input id="ship-box" type="checkbox" />
                            </h3>
                        </div>
                        <div id="ship-box-info" class="row">
                            <div class="col-md-12">
                            <div class="checkout-form-list mrg-nn">
                                <label>Order Notes</label>
                                <textarea name="note" id="checkout-mess" cols="30" rows="5" placeholder="Notes about your order, e.g. special notes for delivery." ></textarea>
                            </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
                </div>
    </div>

<!-- checkout-area end -->
  </v-container>
</template>

<script>
export default {

}
</script>

<style>

</style>
