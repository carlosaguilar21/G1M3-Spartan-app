<template>
  <v-app id="inspire">
    <v-app-bar
      :clipped-left="$vuetify.breakpoint.lgAndUp"
      app
      color="primary"
      dark
    >
<!--      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />-->

      <v-toolbar-title
        style="width: 350px"
      >
        <a href="/" class="white--text" style="text-decoration: none"><v-icon>mdi-weight-lifter</v-icon>&nbsp;SpartanSports</a>
      </v-toolbar-title>
      <v-text-field
        flat
        solo-inverted
        hide-details
        prepend-inner-icon="mdi-magnify"
        label="Search"
        class="hidden-sm-and-down pl-10 ml-4"
      />
      <v-spacer />
      
      <v-btn href="#" icon>
        <v-icon> mdi-facebook </v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-instagram</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-twitter</v-icon>
      </v-btn>
     
      <v-btn v-on="on" href="/cart" icon>
        <v-badge
          content="2"
          value="2"
          color="green"
          overlap
        >
          <v-icon>mdi-shopping</v-icon>
        </v-badge>      
      </v-btn>
      <v-btn v-on="on" href="/registration" icon>
      <v-icon> mdi-account-circle </v-icon>
      </v-btn>
       
    </v-app-bar>
    <v-content>
      <v-bottom-navigation
        :value="activeBtn"
        color="primary"
        horizontal
      >
        <a href="/" class="v-btn">
          <span>Home</span>
        </a>
        <v-menu open-on-hover offset-y>
          <template v-slot:activator="{ on }">
            <v-btn v-on="on">
              <span>Shop</span>
            </v-btn>
          </template>
          <v-card
            class="mx-auto"
            max-width="344"
            outlined
          >

            <v-list-item
              v-for="(item, index) in items"
              :key="index"
              href="/shop"
            >
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item>

          </v-card>
        </v-menu>
        <a href="/product" class="v-btn">
          <span>Product</span>
        </a>
        <v-btn href="/blog">
          <span>Blog</span>
        </v-btn>
      </v-bottom-navigation>
    </v-content>
      <router-view/>
    <v-footer
      :padless="true"
    >
      <v-card
        flat
        tile
        width="100%"
        class="secondary white--text text-center"
      >
        <v-card-text>
          <v-btn
            class="mx-4 white--text"
            icon
          >
            <v-icon size="24px">mdi-home</v-icon>
          </v-btn>
          <v-btn
            class="mx-4 white--text"
            icon
          >
            <v-icon size="24px">mdi-email</v-icon>
          </v-btn>
          <v-btn
            class="mx-4 white--text"
            icon
          >
            <v-icon size="24px">mdi-calendar</v-icon>
          </v-btn>
           <v-btn
            class="mx-4 white--text"
            icon
          >
            <v-icon size="24px">mdi-delete</v-icon>
          </v-btn>

        </v-card-text>

        <v-card-text class="white--text pt-0">
         Un sueño no se hace realidad por arte de magia, necesita sudor, determinación y trabajo duro - Colin Powell. En SpartanSports brindamos productos de alta calidad para la práctica del deporte tanto a nivel profesional como recreativo, ofreciendo soluciones para las distintas necesidades,  utilizando una plataforma tecnológica que simplifique y facilite los procesos de las distintas áreas,  comprometidos a apoyar la salud mental y física de nuestro público..
        </v-card-text>

        <v-divider></v-divider>

        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} — <strong>SpartanSports</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>
<script>
    export default {
        data () {
            return {
                on:{

                },
                items: [
                    { title: 'Baloncesto' },
                    { title: 'Voleibol' },
                    { title: 'Tenis' },
                    { title: 'Futbol' },
                    { title: 'Natación' },
                ],
                activeBtn: 1,
            }
        }
    }
</script>
