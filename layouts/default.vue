<template>
  <v-app>
    <!-- navbar -->
    <v-app-bar
        app
        color="blue darken-3"
        dark

      >
        <v-btn text>
        <v-icon>mdi-phone</v-icon>
        01706494553
      </v-btn>

      <v-divider vertical></v-divider>

      <v-btn text>
         <v-icon> mdi-email</v-icon>
           oceanta.fashion@gmail.com

      </v-btn>
        <v-spacer></v-spacer>
        <v-btn text>
         <v-icon>mdi-home</v-icon>
          Home
      </v-btn>

      <v-divider vertical></v-divider>

      <v-btn text>
        <v-icon>mdi-flag</v-icon>
         Shop
      </v-btn>

      <v-divider vertical></v-divider>

      <v-btn text>
        <v-icon> mdi-email</v-icon>
         My Order
      </v-btn>
      <v-divider vertical></v-divider>

      <v-btn text ><v-icon dark small> mdi-plus </v-icon>sign in</v-btn>
      </v-app-bar>
    <!-- Navbar End-->
    <v-main>
      <v-container>
        <!-- Main content -->
        <nuxt />
        <!--content End-->
      </v-container>
    </v-main>
    <!-- footer -->
    <v-footer class="grey darken-4 py-4 white--text" >
        <div class="container">
            <v-row>
                <v-col cols="8" sm="4">
                    <div class="">
                        <h3 class="head">Contact Us</h3>
                        <div class="">
                            <div class="">
                                <div class="footer-info-icon2">
                                    <span>Address:</span>
                                </div>
                                <div class="footer-info-content2">
                                    <p>76, Middle-Azampur
                                        <br>Dakshinkhan -1230 Dhaka</p>
                                </div>
                            </div>
                            <div class="footer-address-electro">
                                <div class="footer-info-icon2">
                                    <span>Phone:</span>
                                </div>
                                <div class="footer-info-content2">
                                    <p>+880 1680800810
                                        <br>+880 1618600618</p>
                                </div>
                            </div>
                            <div class="footer-address-electro">
                                <div class="footer-info-icon2">
                                    <span>Email:</span>
                                </div>
                                <div class="footer-info-content2">
                                    <p><a href="mailto:oceanta.fashion@gmail.com">oceanta.fashion@gmail.com</a></p>
                                </div>
                            </div>
                        </div>
                    </div>
                </v-col>
                <v-col cols="8" sm="2">
                    <div class="">
                        <h3 class="head">My Account</h3>
                        <div class="link">
                            <ul>
                                <li><a href="http://127.0.0.1:8000/register">Register</a></li>
                                <li><a href="http://127.0.0.1:8000/login">Login Here</a></li>
                                <li><a href="http://127.0.0.1:8000/cart">Cart History</a></li>
                                <li><a href="http://127.0.0.1:8000/shop">Shop</a></li>

                            </ul>
                        </div>
                    </div>
                </v-col>
                <v-col cols="8" sm="2">
                    <div class="">
                        <h3 class="head">Message Us</h3>
                        <div class="link">
                            <ul>
                                <li><a href="https://www.facebook.com/messages/t/OceantaFashion">Messanger</a></li>
                                <li><a href="tel:01680800810">Whatsapp</a></li>
                                <li><a href="tel:01680800810">Imo</a></li>
                                <li><a href="tel:01680800810">Viber</a></li>
                            </ul>
                        </div>
                    </div>
                </v-col>
                <v-col cols="8" sm="2">
                    <div class="">
                        <h3 class="head">Follow Us</h3>
                        <div class="link">
                            <ul>
                                <li><a href="https://www.facebook.com/OceantaFashion">Facebook</a></li>
                                <li><a href="https://www.instagram.com/oceanta_fashion/">Instagram</a></li>
                                <li><a href="https://twitter.com/oceanta_fashion">Twitter</a></li>
                                <li><a href="#">Youtube</a></li>
                            </ul>
                        </div>
                    </div>
                </v-col>
            </v-row>

        </div>
</v-footer>
<v-card>
  <v-row no-gutters
       class="grey darken-3 py-2 text-center white--text "
       >
      <v-col

        cols="12"
        sm="4"
      >
         <small>Help Center</small>
      </v-col>
      <v-spacer></v-spacer>
      <v-col

        cols="12"
        sm="4"
      >
       <span>Copyright © Oceanta Fashion 2020 . All Right Reserved.</span>
      </v-col>
    </v-row>
</v-card>
    <!-- footer End-->
  </v-app>
</template>

<script>

export default {
  data () {
    return {
      fixed: false,
      title: 'Storefront'
    }
  }
}
</script>
<style>
h1 {
    margin-top:10px;
    font-size: 25px;
    padding: 10px;
}

.container{
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    flex-direction: row;
    width: 950px;
}
.sec.about {
     margin-right: 5px;
     width: 60%;
}
h2 {
    position: relative;
    color: black;
    font-weight: 500;
    margin-bottom: 15px;
}
.footer.container .sec .about h2:before {
    content: '';
    position: absoulate;
    bottom: -5px;
    left: 0;
    width: 50px;
    height: 2px;
    background: #f00;
}
footer .container .sec.aboutus p{
    color: #999;
}

h3.head {
    font-size: 22px;
    margin-bottom: 5px;
    padding: 5px;
    color: red;
}
li {
    list-style-type: none;
    line-height: 30px;
}


</style>
