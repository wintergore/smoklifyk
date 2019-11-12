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
    <v-app-bar
      app
      dark
      color="rgba(0,0,0,.35)"
      height="50"
      hide-on-scroll

    >
      <template v-slot:img="{ props }">
        <g-image
          v-bind="props"
          gradient="to top right, rgba(100,115,201,.7), rgba(25,32,72,.7)"
          src="/uploads/002.jpg"
        ></g-image>
      </template>
      <v-spacer />
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />

      <v-toolbar-title>{{ $static.metadata.siteName }}</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
      <v-spacer />
      <template v-slot:extension>
        <v-tabs
          align-with-title
          background-color="transparent"
        >
        <v-spacer />
          <v-tab to="/">Home</v-tab>
          <v-tab to="/about/">About Us</v-tab>
          <v-tab>Corporate</v-tab>
          <v-tab>Weddings</v-tab>
          <v-tab>Ethics</v-tab>
          <v-tab>Contact</v-tab>
          <v-tab>Gallery</v-tab>
          <v-spacer />
        </v-tabs>
      </template>
    </v-app-bar>
    <!-- <v-parallax height="300" src="https://picsum.photos/1920/1080?random"></v-parallax> -->
    <!-- <v-app-bar
      app
      clipped-left
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title><g-link to="/">{{ $static.metadata.siteName }}</g-link></v-toolbar-title>
    </v-app-bar> -->

    <v-content><!-- class="pt-0" -->
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

<style>
</style>
