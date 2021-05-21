<template>
  <div>
    <!--Top Navbar-->
    <v-toolbar flat class="mainHeader hidden-sm-and-down" color="grey lighten-4">
      <v-toolbar-items class="flex justify-start mt-5">
      <div>
          <NuxtLink to="/" style="text-decoration: none; color: inherit;">
            <v-btn plain><v-icon>mdi-home</v-icon> Home </v-btn>
          </NuxtLink>
          <NuxtLink to="/shop" style="text-decoration: none; color: inherit;">
            <v-btn plain><v-icon>mdi-storefront</v-icon>Shop</v-btn>
          </NuxtLink>
           <NuxtLink to="/shop" style="text-decoration: none; color: inherit;">
            <v-btn plain><v-icon>mdi-storefront</v-icon>Pages</v-btn>
          </NuxtLink>
           <NuxtLink to="/shop" style="text-decoration: none; color: inherit;">
            <v-btn plain><v-icon>mdi-storefront</v-icon>Element</v-btn>
          </NuxtLink>
        </div>

      </v-toolbar-items>
      <!-- desktop -->
      <v-toolbar-title class="">
        <v-toolbar-title class="ml-10 hidden-sm-and-down"><span>OCENTA</span></v-toolbar-title>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <!-- desktop -->
      <v-toolbar-items class="flex justify-end mt-5">
        <div>
          <v-icon class="mr-1">
            mdi-heart
          </v-icon>
          <NuxtLink to="/login" style="text-decoration: none; color: inherit;">
            <v-btn plain v-if="!loggedIn"><v-icon>mdi-login</v-icon>Login</v-btn>
          </NuxtLink>
          <NuxtLink to="/profile" style="text-decoration: none; color: inherit;">
            <v-btn plain v-if="loggedIn"><v-icon>mdi-account</v-icon>Profile</v-btn>
          </NuxtLink>
        </div>
        <div>
          <v-btn plain class="" @click.stop="right = !right"><v-icon class="mr-1">mdi-cart</v-icon>my cart</v-btn>
        </div>
      </v-toolbar-items>
    </v-toolbar>
    <!--Top Navbar End-->

    <!--mobile Nav-->
    <v-toolbar flat class="mainHeader hidden-md-and-up" color="grey lighten-4">
      <v-toolbar-title class="">
        <v-toolbar-title class="ml-10"><span>LOGO</span></v-toolbar-title>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="flex justify-end mt-5">
        <div>
          <NuxtLink to="/login" style="text-decoration: none; color: inherit;">
            <v-btn plain v-if="!loggedIn"><v-icon>mdi-login</v-icon>Login</v-btn>
          </NuxtLink>
          <NuxtLink to="/profile" style="text-decoration: none; color: inherit;">
            <v-btn plain v-if="loggedIn"><v-icon>mdi-account</v-icon>Profile</v-btn>
          </NuxtLink>
        </div>
        <div>
          <v-btn plain class="" @click.stop="right = !right"><v-icon class="mr-1">mdi-cart</v-icon>my cart</v-btn>
        </div>
      </v-toolbar-items>
    </v-toolbar>
    <!--mobile Nav-->

    <!-- <v-btn plain><v-text-field class="mt-5" prepend-inner-icon="mdi-magnify" placeholder="Search Here"></v-text-field></v-btn> -->
    <!-- right sidebar -->
    <v-navigation-drawer v-model="right" fixed right temporary width="300">
      <v-list dense>
      <v-list-item link>
        <v-list-item-action>
          <v-icon>mdi-shopping basket</v-icon>
        </v-list-item-action>
        <v-list-item-content>
          <v-list-item-title>MY BAG</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
      <v-divider></v-divider>
      <v-container class="grey lighten-5">
        <v-row no-gutters>
          <v-col>
            <v-img width="100" height="180" src="https://i.pinimg.com/originals/cc/ab/e5/ccabe55eba2e9419388c946addaa9f2d.jpg"></v-img>
          </v-col>
          <v-col order="1">
                <v-col xs="2">
                <div>$ 3.00</div>
              </v-col>
              <v-col >
                <div>T-shirt</div>
              </v-col>
              <v-col xs="2">
                <div class="caption grey--text">XXL</div>
              </v-col>
          </v-col>
          <v-col order="1">
          <div class="mt-5 text-center">Qty: 1</div>
          </v-col>
        </v-row>
      </v-container>
      <div class="row">
        <v-simple-table class="text-center mt-10">
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
      </div>
      <v-btn rounded color="primary"  dark class=" mt-10">
          <NuxtLink to="/checkOut" style="text-decoration: none; color: inherit;" >Checkout</NuxtLink>
      </v-btn>
    </v-list>
    </v-navigation-drawer>
    <!--Sub Navbar End-->
     <!-- right sidebar -->
    <v-navigation-drawer v-model="left" fixed left temporary width="300">
      <v-list dense>
      <v-list-item link>
        <v-list-item-action>
          <v-icon>mdi-shopping basket</v-icon>
        </v-list-item-action>
        <v-list-item-content>
          <v-list-item-title>Logo</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
      <v-divider></v-divider>
    </v-list>
    </v-navigation-drawer>
    <!--Sub Navbar End-->
  </div>
</template>

<script>
export default {
  name: "Navbar",
  props:{
    source: String,
    },
    data () {
      return {
      right: null,
      right: false,
      left: null,
      left: false,
      loggedIn:false,
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
    }
    },
}
</script>

<style >
.removeLine{
    text-decoration: none;
    color: grey;
 }
 span:hover {
  cursor: pointer;
  color: tomato;
}
</style>
