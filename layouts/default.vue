<template>
  <v-app v-cloak>
    <v-app-bar app style="color: white">
      <v-navigation-drawer
        v-model="drawer"
        absolute
        temporary
        app
        width="150"
        height="340">
        <v-list class="pt-4">
          <v-list-tile active-class="green--text" to="/">
            <v-list-tile-content>
              <v-list-tile-title>HOME</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
          <v-list-tile active-class="green--text" to="/resume">
            <v-list-tile-content>
              <v-list-tile-title>RESUME</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
          <v-list-tile active-class="green--text" to="/services">
            <v-list-tile-content>
              <v-list-tile-title>SERVICES</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
          <v-list-tile active-class="green--text" to="/portfolio">
            <v-list-tile-content>
              <v-list-tile-title>PORTFOLIO</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
          <v-list-tile active-class="green--text" to="/blog">
            <v-list-tile-content>
              <v-list-tile-title>BLOG</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
          <v-list-tile active-class="green--text" to="/contact">
            <v-list-tile-content>
              <v-list-tile-title>CONTACT</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-navigation-drawer>
      <v-toolbar flat dense color="transparent" scroll-off-screen>
        <v-toolbar-side-icon class="hidden-md-and-up" @click.stop="drawer = !drawer" />
        <v-toolbar-title class="headline">
          <span class="font-weight-light">Bruin</span>
          <span class="indigo--text">Kuma</span>
        </v-toolbar-title>
        <v-spacer />
        <v-btn @click="changeTheme" depressed small icon class="hidden-md-and-up">
          <v-icon v-if="goDark==true">fas fa-sun</v-icon>
          <v-icon v-else>fas fa-moon</v-icon>
        </v-btn>
        <v-toolbar-items class="hidden-sm-and-down">
          <v-btn text to="/" active-class="indigo--text headline">Home</v-btn>
          <v-btn text to="/resume" active-class="indigo--text headline">Resume</v-btn>
          <v-btn text to="/portfolio" active-class="indigo--text headline">Portfolio</v-btn>
          <v-btn text to="/contact" active-class="indigo--text headline">Contact</v-btn>
          <v-btn @click="changeTheme" depressed small icon>
            <v-icon v-if="goDark==true">fas fa-sun</v-icon>
            <v-icon v-else>fas fa-moon</v-icon>
          </v-btn>
        </v-toolbar-items>
      </v-toolbar>
    </v-app-bar>

    <v-main fluid>
      <nuxt />
    </v-main>

    <v-footer app color="#0F4C81">
      <v-spacer />
      <span style="color: white">&copy; 2021</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      drawer: null
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
