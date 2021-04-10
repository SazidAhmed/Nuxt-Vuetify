<template>
    <div>
        <!--Top Navbar-->
        <v-toolbar flat class="mainHeader" color="grey lighten-4">
            <v-toolbar-title class="ml-5 hidden-sm-and-down">
                <v-btn plain>
                    <v-icon class="mr-1">mdi-phone</v-icon>
                    01706494553
                </v-btn>
                <v-btn plain>
                    <v-icon class="mr-1"> mdi-email</v-icon>
                    oceanta@gmail.com
                </v-btn>
            </v-toolbar-title>
            <v-spacer></v-spacer>
            <v-toolbar-items class="hidden-sm-and-down mr-10">
                <v-btn plain><v-icon>mdi-home</v-icon> <NuxtLink to="/" style="text-decoration: none; color: inherit;">Home</NuxtLink></v-btn>
                <v-btn plain><v-icon>mdi-storefront</v-icon><NuxtLink to="/shop" style="text-decoration: none; color: inherit;">Shop</NuxtLink></v-btn>
                <v-btn plain><v-icon>mdi-login</v-icon><NuxtLink to="/login" style="text-decoration: none; color: inherit;">Login</NuxtLink></v-btn>
                <v-btn plain><v-icon>mdi-account</v-icon><NuxtLink to="/register" style="text-decoration: none; color: inherit;">Register</NuxtLink></v-btn>
                <v-btn plain><v-icon>mdi-home</v-icon><NuxtLink to="/extra" style="text-decoration: none; color: inherit;">Extra</NuxtLink></v-btn>
            </v-toolbar-items>
        </v-toolbar>
        <!--Top Navbar End-->
        <!--Sub Navbar-->
        <v-toolbar flat color="grey lighten-4">
            <v-toolbar-title class="ml-10 hidden-sm-and-down">LOGO</v-toolbar-title>
               <div class="hidden-md-and-up">
                <v-menu offset-y>
                <template v-slot:activator="{ on }">
                    <v-app-bar-nav-icon v-on="on"></v-app-bar-nav-icon>
                </template>
                <v-list class="responsiveMenu">
                    <v-list-item>
                    <v-list-item-title><router-link to="/">Home</router-link></v-list-item-title>
                    </v-list-item>
                    <v-list-item>
                    <v-list-item-title><router-link to="/shop">Shop</router-link></v-list-item-title>
                    </v-list-item>
                    <v-list-item>
                    <v-list-item-title><router-link to="/login">Login</router-link></v-list-item-title>
                    </v-list-item>
                    <v-list-item>
                        <v-list-item-title><router-link to="/register">Register</router-link></v-list-item-title>
                    </v-list-item>
                    <v-list-item>
                        <v-list-item-title><router-link to="/register">Profile</router-link></v-list-item-title>
                    </v-list-item>
                    <v-list-item>
                        <v-list-item-title><router-link to="/extra">Extra</router-link></v-list-item-title>
                    </v-list-item>
                </v-list>
                </v-menu>
            </div>
            <v-spacer></v-spacer>
            <div class="hidden-md-and-up ml-10">
                <v-btn text>
                   <h2>Logo</h2>
                </v-btn>
            </div>
            <v-spacer></v-spacer>
            <v-toolbar-items class="hidden-sm-and-down">
                <v-btn plain>
                    <v-text-field
                        class="mt-5"
                        prepend-inner-icon="mdi-magnify"
                        placeholder="Search Here"
                    ></v-text-field>
                </v-btn>
                <v-btn plain>
                    <v-icon class="mr-1">mdi-account</v-icon>
                    Profile
                </v-btn>
                <v-btn plain class="mr-10" @click.stop="right = !right">
                    <v-icon class="mr-1">mdi-cart</v-icon>
                    my cart
                </v-btn>
            </v-toolbar-items>
            <div class="hidden-md-and-up">
              <v-btn @click.stop="right = !right"><v-icon>mdi-cart</v-icon>my cart</v-btn>

            </div>
        </v-toolbar>
       <v-navigation-drawer v-model="right" fixed right temporary>
         <v-list dense>
          <v-list-item link>
            <v-list-item-action>
              <v-icon>mdi-home</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>Home</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
            <v-list-item link>
               <v-list-item-action>
                 <v-icon>mdi-email</v-icon>
              </v-list-item-action>
              <v-list-item-content>
                 <v-list-item-title>Contact</v-list-item-title>
              </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
        <!--Sub Navbar End-->
    </div>
</template>

<script>
export default {
    name: "Navbar",
    props: {
            source: String,
         },
     data: () => ({
            right: null,
            right: false,
          }),
}
</script>

<style >
.removeLine{
    text-decoration: none;
    color: grey;
 }
</style>
