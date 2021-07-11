<template>
  <v-app v-cloak>
    <v-app-bar app color="#41b883" style="color: white">
      <v-app-bar-nav-icon color="white" @click="drawer = true" />
      <v-toolbar-title>
        SAMPLE
      </v-toolbar-title>
      <v-spacer />
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" fixed temporary>
      <v-list nav dense>
        <v-list-item-group
          v-model="group"
          active-class="indigo--text text--accent-4"
        >
          <nuxt-link v-scroll-to="'#profile'" to>
            <v-list-item>
              <v-list-item-icon>
                <v-icon>mdi-account</v-icon>
              </v-list-item-icon>
              <v-list-item-title>
                profile
              </v-list-item-title>
            </v-list-item>
          </nuxt-link>
          <nuxt-link v-scroll-to="'#work'" to>
            <v-list-item>
              <v-list-item-icon>
                <v-icon>mdi-folder</v-icon>
              </v-list-item-icon>
              <v-list-item-title>
                work
              </v-list-item-title>
            </v-list-item>
          </nuxt-link>
          <nuxt-link v-scroll-to="'#contact'" to>
            <v-list-item>
              <v-list-item-icon>
                <v-icon>mdi-email</v-icon>
              </v-list-item-icon>
              <v-list-item-title>
                contact
              </v-list-item-title>
            </v-list-item>
          </nuxt-link>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <v-content fluid>
      <nuxt />
    </v-content>

    <v-footer app color="#41b883">
      <v-spacer />
      <span style="color: white">&copy; 2020 Sample. All Rights Reserved.</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      drawer: false,
      group: null
    }
  }
}
</script>
<style>
[v-cloak] {
  display: none;
}

.v-application a {
  color: black;
  text-decoration: none;
}

.theme--light.v-btn:hover::before {
  opacity: 0.2;
}
</style>
