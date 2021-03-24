<template>
 <v-app class="grey lighten-5 white-text">
    <v-app id="inspire">
      <v-row class="">
        <v-col
          cols="auto"
          lg="3"
        >
          <v-card
            class="pa-2 "
            outlined
            tile
          >
            .col-auto
          </v-card>
        </v-col>
        <v-spacer></v-spacer>
        <v-col md="5">
            <v-text-field
            flat
            solo-inverted
            hide-details
            prepend-inner-icon="mdi-magnify"
            label="Search"
            class="hidden-sm-and-down"
          ></v-text-field>
          <v-spacer></v-spacer>

        </v-col>
        <v-spacer></v-spacer>
        <v-col >
          <v-icon>mdi-cart</v-icon>
            my cart
        </v-col>
      </v-row>
      <!---slider--->
      <v-carousel
        cycle
        height="400"
        hide-delimiter-background
        show-arrows-on-hover
      >
        <template v-slot:prev="{ on, attrs }">
          <v-btn
            color="grey"
            v-bind="attrs"
            v-on="on"
          >Previous slide</v-btn>
        </template>
        <template v-slot:next="{ on, attrs }">
          <v-btn
            color="grey"
            v-bind="attrs"
            v-on="on"
          >Next slide</v-btn>
        </template>
        <v-carousel-item
          v-for="(item,i) in items"
          :key="i"
          :src="item.src"
        >
          <v-row
            class="fill-height"
            align="center"
            justify="center"
          >
            <div class="display-3">
              <h1 >new pic</h1>
              <p>thats the new style</p>
              <v-btn>Shop Now</v-btn>
            </div>
          </v-row>
        </v-carousel-item>
      </v-carousel>
      <!---slider--->
      <!----boxhover---->
      <v-container>
        <v-row class="py-4">
          <v-col
            cols="12"
            sm="3"
          >
          <v-hover
            v-slot="{ hover }"
            open-delay="200"
          >
            <v-card
            :elevation="hover ? 16 : 100"
            :class="{ 'on-hover': hover }"
            class="mx-auto"
            height="220"

          >

              <v-img height="100%" src="https://previews.123rf.com/images/marinini/marinini1303/marinini130300014/18302881-text-24-7-service-3d-red-white-banner-letters-and-block-business-concept.jpg"></v-img>

            </v-card>
          </v-hover>
          </v-col>
          <v-col
            cols="12"
            sm="3"
          >
            <v-hover
              v-slot="{ hover }"
              open-delay="200"
            >
              <v-card
                :elevation="hover ? 16 : 4"
                :class="{ 'on-hover': hover }"
                class="mx-auto"
                height="220"


              >
              <v-img height="100%" src="https://www.malabarshopping.com/image/data/cod-malabar-shopping.png"></v-img>
              </v-card>
            </v-hover>
          </v-col>
          <v-col
            cols="12"
            sm="3"
          >
            <v-hover
              v-slot="{ hover }"
              close-delay="200"
            >
              <v-card
                :elevation="hover ? 8 : 45"
                :class="{ 'on-hover': hover }"
                class="mx-auto"
                height="220"


              >
                <v-img height="100%" src="https://st2.depositphotos.com/1014014/7994/i/950/depositphotos_79944016-stock-photo-24-7-service-cycle-sign.jpg"></v-img>
              </v-card>
            </v-hover>
          </v-col>
        </v-row>
      </v-container>
      <!----Latest Product---->
      <div class="sec">
          <h2 class="text-center">
            Latest Product
          </h2>
      </div>
      <!---FEATURED PRODUCTS---->
      <v-continer class="py-5">
        <div class="cont">
          <div class="section">
              <h2 class="text-center">
                FEATURED PRODUCTS
              </h2>

            <v-row class="pa-5 ma-5 ">
              <v-col
                cols="6"
                sm="4"
              >
              <v-hover>
              <template v-slot:default="{ hover }">
                <v-card
                  class="mx-auto"
                  max-width="350"
                >
                  <v-img height="300" src="https://static.ajkerdeal.com/images/deals/391900212195302/smallimage1.jpg"></v-img>
                  <v-fade-transition>
                    <v-overlay
                      v-if="hover"
                      absolute
                      color="#036358"
                    >
                      <v-btn icon><v-icon>mdi-cart</v-icon></v-btn>
                      <v-btn icon><v-icon>mdi-eye</v-icon></v-btn>
                    </v-overlay>
                  </v-fade-transition>
                </v-card>
              </template>
            </v-hover>

                </v-col>

                <v-col
                  cols="6"
                  sm="4"
                >
                  <v-hover>
                <template v-slot:default="{ hover }">
                  <v-card
                    class="mx-auto"
                    max-width="350"
                  >
                    <v-img height="300" src="https://www.rightchoice.com.bd/media/catalog/product/cache/1/small_image/300x300/77c94543c5e78217e7ff5d5962f2ed86/l/x/lx_6637-1_jpg_02061805070811.jpg.png"></v-img>
                    <v-fade-transition>
                      <v-overlay
                        v-if="hover"
                        absolute
                        color="#036358"
                      >
                        <v-btn icon><v-icon>mdi-cart</v-icon></v-btn>
                        <v-btn icon><v-icon>mdi-eye</v-icon></v-btn>
                      </v-overlay>
                    </v-fade-transition>
                  </v-card>
                </template>
              </v-hover>
              </v-col>

              <v-col
                cols="6"
                sm="4"
              >
              <v-hover>
              <template v-slot:default="{ hover }">
                <v-card
                  class="mx-auto"
                  max-width="350"
                >
                  <v-img height="300" src="https://images.othoba.com/images/thumbs/0197816_womens-georgette-embroidery-un-stitched-three-piece-replica-ctb-d-no-452_300.jpeg"></v-img>
                  <v-fade-transition>
                    <v-overlay
                      v-if="hover"
                      absolute
                      color="#036358"
                    >
                      <v-btn icon><v-icon>mdi-cart</v-icon></v-btn>
                      <v-btn icon><v-icon>mdi-eye</v-icon></v-btn>
                    </v-overlay>
                  </v-fade-transition>
                </v-card>
              </template>
            </v-hover>
              </v-col>
            </v-row>
          </div>
        </div>
      </v-continer>
      <!---Latest products---->
      <!---Featured products---->
      <v-continer class="py-5">
        <div class="cont">
          <div class="section">
            <h2 class="text-center">
              BEST SELLINGS
            </h2>
            <v-row class="pa-5 ma-5 ">
                <v-col
                cols="6"
                sm="4"
              >
              <v-hover>
              <template v-slot:default="{ hover }">
                <v-card
                  class="mx-auto"
                  max-width="344"
                >
                  <v-img height="300" src="https://www.rightchoice.com.bd/media/catalog/product/cache/1/small_image/300x300/77c94543c5e78217e7ff5d5962f2ed86/l/x/lx_6633-1_jpg_02061805025280.jpg.png"></v-img>
                  <v-fade-transition>
                    <v-overlay
                      v-if="hover"
                      absolute
                      color="#036358"
                    >
                      <v-btn icon><v-icon>mdi-cart</v-icon></v-btn>
                      <v-btn icon><v-icon>mdi-eye</v-icon></v-btn>
                    </v-overlay>
                  </v-fade-transition>
                </v-card>
              </template>
              </v-hover>

                </v-col>
                <v-col
                  cols="6"
                  sm="4"
                >
                  <v-hover>
                <template v-slot:default="{ hover }">
                  <v-card
                    class="mx-auto"
                    max-width="344"
                  >
                    <v-img height="300" src="https://www.rightchoice.com.bd/media/catalog/product/cache/1/small_image/300x300/77c94543c5e78217e7ff5d5962f2ed86/l/x/lx_6634-1_jpg_02061805034604.jpg.png"></v-img>
                    <v-fade-transition>
                      <v-overlay
                        v-if="hover"
                        absolute
                        color="#036358"
                      >
                        <v-btn icon><v-icon>mdi-cart</v-icon></v-btn>
                        <v-btn icon><v-icon>mdi-eye</v-icon></v-btn>
                      </v-overlay>
                    </v-fade-transition>
                  </v-card>
                </template>
              </v-hover>
                </v-col>

              <v-col
                cols="6"
                sm="4"
              >
              <v-hover>
              <template v-slot:default="{ hover }">
                <v-card
                  class="mx-auto"
                  max-width="344"
                >
                  <v-img height="300" src="https://www.rightchoice.com.bd/media/catalog/product/cache/1/small_image/300x300/77c94543c5e78217e7ff5d5962f2ed86/l/x/lx_6637_jpg_02061805064831.jpg.png"></v-img>
                  <v-fade-transition>
                    <v-overlay
                      v-if="hover"
                      absolute
                      color="#036358"
                    >
                      <v-btn icon><v-icon>mdi-cart</v-icon></v-btn>
                      <v-btn icon><v-icon>mdi-eye</v-icon></v-btn>
                    </v-overlay>
                  </v-fade-transition>
                </v-card>
              </template>
            </v-hover>
              </v-col>
            </v-row>
          </div>
        </div>
      </v-continer>
      <!---Featured products---->
      <!---Best Sellings---->
      <v-continer class="py-5">
        <v-card height="100px">
          <div class="container">
                <div class="section">
                    <h2>Best Sellings</h2>
                </div>
            </div>
        </v-card>
      </v-continer>
      <!---Best Sellings---->
    </v-app>
  </v-app>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: { Logo, VuetifyLogo},
  data () {
      return {
        items: [
          {
            src: 'https://i.pinimg.com/originals/18/5e/8b/185e8ba71c2bff728de42b68376bdc47.jpg',
          },
          {
            src: 'https://live.staticflickr.com/4503/36937082504_ee60c1c4ba_b.jpg',
          },
          {
            src: 'https://i.ytimg.com/vi/Ai7k3rI21H8/maxresdefault.jpg',
          },
          {
            src: 'https://static-01.daraz.com.bd/p/4daa49d124da7083b3882143bc64e7c5.jpg',
          },
        ],
      }
    },
}
</script>

<style>

.v-card--reveal {
  align-items: center;
  bottom: 0;
  justify-content: center;
  opacity: .5;
  position: absolute;
  width: 100%;
}
.section > h2 {

    font-size: 30px;
    font-weight: bold;
    margin: 0;
    position: relative;
    text-transform: uppercase;
    letter-spacing: 1;
}
.sec > h2 {

    font-size: 25px;
    font-weight: bold;
    margin: 0;
    position: relative;
    text-transform: uppercase;
    letter-spacing: 1;
}
.mt-5, .my-5 {
    margin-top: 3rem!important;
}

.text-center {
    text-align: center!important;
}
.sec > h2::before {
    background-color: #49a514;
    content: "";
    height: 2px;
    left: -81px;
    position: absolute;
    top: 19px;
    width: 60px;
}
*, ::after, ::before {
    box-sizing: border-box;
}
.sec > h2::after {
    background-color: #49a514;
    content: "";
    height: 2px;
    position: absolute;
    right: -81px;
    top: 19px;
    width: 60px;
}

.section > h2::before {
    background-color: #49a514;
    content: "";
    height: 2px;
    left: -81px;
    position: absolute;
    top: 19px;
    width: 60px;
}
*, ::after, ::before {
    box-sizing: border-box;
}
.section > h2::after {
    background-color: #49a514;
    content: "";
    height: 2px;
    position: absolute;
    right: -81px;
    top: 19px;
    width: 60px;
}
</style>
