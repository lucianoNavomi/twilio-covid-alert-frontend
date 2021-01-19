<template>
  <v-app>

    <!-- <v-app-bar
      color="primary"
      app
      permanent
      dark
    >
    
      <div class="d-flex align-center">
        COVID Alerts Subscription System
      </div>

      <v-spacer></v-spacer>
    </v-app-bar> -->
      <!-- <v-system-bar color="deep-purple darken-3"></v-system-bar> -->

      <v-app-bar
        color="primary"
        dark
        app
        permanent
      >

        <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
        
        <div class="d-flex align-center">
          COVID Alerts Subscription System
        </div>

        <!-- <v-toolbar-title>My files</v-toolbar-title> -->

        <v-spacer></v-spacer>

      </v-app-bar>

      <v-navigation-drawer
        v-model="drawer"
        absolute
        bottom
        temporary
      >
        <v-list
          nav
          dense
        >
          <v-list-item-group
            v-model="group"
            active-class="indigo--text text--accent-4"
          >
            <v-list-item to="/">
              <v-list-item-title>Subscribe</v-list-item-title>
            </v-list-item>

            <v-list-item to="/admin">
              <v-list-item-title>Admin</v-list-item-title>
            </v-list-item>

          </v-list-item-group>
        </v-list>
      </v-navigation-drawer>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
  export default {
    name: "App",
    data: () => ({
      drawer: false,
      group: null,
    }),

    watch: {
      group () {
        this.drawer = false
      },
    }
  };
</script>