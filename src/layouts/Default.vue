<template>
  <v-app id="app" >
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
      color="#6A76AB"
      dark
      shrink-on-scroll
      prominent
      src="https://picsum.photos/1920/1080?random"
      fade-img-on-scroll
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(100,115,201,.7), rgba(25,32,72,.7)"
        ></v-img>
      </template>

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

      <template v-slot:extension>
        <v-tabs
          align-with-title
          background-color="transparent"
        >
          <v-tab>Home</v-tab>
          <v-tab>About Us</v-tab>
          <v-tab>Corporate</v-tab>
          <v-tab>Weddings</v-tab>
          <v-tab>Ethics</v-tab>
          <v-tab>Contact</v-tab>
          <v-tab>Gallery</v-tab>
        </v-tabs>
      </template>
    </v-app-bar>
    <!-- <v-app-bar
      app
      clipped-left
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title><g-link to="/">{{ $static.metadata.siteName }}</g-link></v-toolbar-title>
    </v-app-bar> -->

    <v-content id="scrolling-techniques-3">
      <v-container
        
        class="fill-height"
        fluid
      >
        <v-row no-gutters class="ma-3">
          <slot />
        </v-row>
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
      drawer: null,
    }),
    created () {
      //this.$vuetify.theme.dark = true
    },
  }
</script>

<style>
</style>
