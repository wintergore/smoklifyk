<template>
  <v-app id="app">
    <v-navigation-drawer
      v-model="drawer"
      app
      clipped
    >
      <v-list dense>
        <v-list-item link to="/about/">
          <v-list-item-action>
            <v-icon>mdi-view-dashboard</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Dashboard</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <!-- worry about all the fancy shit after you have the actual content done. -->
    <!-- then just have a thing at the top -->
    <!-- page scroll listener, toggles inverted scroll flag. -->
    <v-app-bar
      app
      dark
      color="rgba(0,0,0,.15)"
      shrink-on-scroll
      
      height="100"
    >
      <template v-slot:img="{ props }">
        <g-image
          v-bind="props"
          style="background-color:rgba(0,0,0,.15); width: 100%; height: 100%;"
        ></g-image>
      </template>
      
      <v-app-bar-nav-icon v-if="$vuetify.breakpoint.smAndDown" @click.stop="drawer = !drawer" />
      
      <v-tabs
          align-with-title
          background-color="transparent"
        >
          <v-spacer />
          <v-tab to="/">Home</v-tab>
          <v-tab to="/about/">About Us</v-tab>
          <v-tab>Corporate</v-tab>
          <div style="width: 180px;" class="d-flex align-center justify-center">
          <g-image src="/logo.png" style="height: 100%;" class="align-self-center py-3" />
          </div>
          <v-tab>Weddings</v-tab>
          <v-tab>Ethics</v-tab>
          <v-tab>Contact</v-tab>
          <v-tab>Gallery</v-tab>
          <v-spacer />
        </v-tabs>
        
    </v-app-bar>
    <!-- <v-parallax height="300" src="https://picsum.photos/1920/1080?random"></v-parallax> -->
    <!-- <v-app-bar
      app
      clipped-left
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title><g-link to="/">{{ $static.metadata.siteName }}</g-link></v-toolbar-title>
    </v-app-bar> -->

    <v-content class="pt-0">
      <v-container
        class="fill-height pa-0"
        fluid
      >
        <slot />
      </v-container>
    </v-content>

    <v-footer app>
      <span>&copy; 2019</span>
    </v-footer>
  </v-app>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
  export default {
    props: {
      source: String,
    },
    data: () => ({
      drawer: false,
    }),
    created () {
      //this.$vuetify.theme.dark = true
    },
  }
</script>

<style lang="scss">
// .v-application .v-application--wrap header {
//   color: red;
//   &.v-app-bar--is-scrolled {
//   color: red !important;
//   background-color: rgba(0,0,0,.95) !important;
// }
// }
// .v-app-bar--is-scrolled {
//   color: red;
//   background-color: rgba(0,0,0,.95);
// }
</style>
