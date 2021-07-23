<template>
  <v-app v-cloak>
    <v-navigation-drawer v-model="drawer" app floating temporary>
      <v-list-item>
        <v-list-item-title class="title">
          Menu
        </v-list-item-title>
      </v-list-item>
      <v-divider />
      <v-list nav>
        <v-list-item v-for="menu in menus" :key="menu.title" :to="menu.url">
          <v-list-item-icon>
            <v-icon>{{ menu.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ menu.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar app>
      <!-- アプリケーションバー -->
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title class="headline">
        <span class="font-weight-light">Bruin</span>
        <span class="indigo--text">Kuma</span>
      </v-toolbar-title>
      <v-spacer />
      <v-btn depressed small icon class="hidden-md-and-up" @click="changeTheme">
        <v-icon v-if="goDark==true">
          fas fa-sun
        </v-icon>
        <v-icon v-else>
          fas fa-moon
        </v-icon>
      </v-btn>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn text to="/" active-class="indigo--text headline">
          Home
        </v-btn>
        <v-btn text to="/resume" active-class="indigo--text headline">
          Resume
        </v-btn>
        <v-btn text to="/portfolio" active-class="indigo--text headline">
          Portfolio
        </v-btn>
        <v-btn text to="/contact" active-class="indigo--text headline">
          Contact
        </v-btn>
        <v-btn depressed small icon @click="changeTheme">
          <v-icon v-if="goDark==true">
            fas fa-sun
          </v-icon>
          <v-icon v-else>
            fas fa-moon
          </v-icon>
        </v-btn>
      </v-toolbar-items>
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
  props: {
    goDark: {
      type: Boolean
    }
  },
  data () {
    return {
      drawer: false,
      menus: [
        { title: 'HOME', icon: 'fas fa-home', url: '/' },
        { title: 'RESUME', icon: 'fas fa-address-card', url: '/resume' },
        { title: 'PORTFOLIO', icon: 'fas fa-heart', url: '/portfolio' },
        { title: 'CONTACT', icon: 'fas fa-envelope', url: '/contact' }
      ]
    }
  },
  methods: {
    changeTheme () {
      this.$emit('changeTheme', this.goDark)
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
