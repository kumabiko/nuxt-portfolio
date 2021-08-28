<template>
  <v-app v-cloak>
    <!-- ナビゲーションドロワー -->
    <v-navigation-drawer v-model="drawer" app floating temporary>
      <v-layout column align-center>
        <v-flex mt-5>
          <v-avatar
            size="100"
          >
            <v-img src="/image/bear_icon.png" />
          </v-avatar>
          <p class="mt-2 text-center">
            くまろー
          </p>
        </v-flex>
      </v-layout>
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
    <!-- アプリケーションバー -->
    <v-app-bar app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-spacer
        class="hidden-md-and-up"
      />
      <v-toolbar-title center class="headline">
        <span class="primary--text">Cool</span>
        <span class="font-weight-light">Bruin</span>
      </v-toolbar-title>
      <v-spacer />
      <v-btn depressed small icon class="hidden-md-and-up" @click="changeTheme">
        <v-icon v-if="goDark==true">
          fas fa-moon
        </v-icon>
        <v-icon v-else>
          fas fa-sun
        </v-icon>
      </v-btn>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn text to="/" active-class="primary--text">
          Home
        </v-btn>
        <v-btn text to="/resume" active-class="primary--text">
          Resume
        </v-btn>
        <v-btn text to="/portfolio" active-class="primary--text">
          Portfolio
        </v-btn>
        <v-btn text to="/contact" active-class="primary--text">
          Contact
        </v-btn>
        <v-btn depressed small icon @click="changeTheme">
          <v-icon v-if="goDark==true">
            fas fa-moon
          </v-icon>
          <v-icon v-else>
            fas fa-sun
          </v-icon>
        </v-btn>
      </v-toolbar-items>
    </v-app-bar>

    <v-main>
      <v-container fluid>
        <v-row>
          <v-col cols="12" md="3">
            <!-- レフトサイドバー -->
          </v-col>
          <v-col cols="12" md="6">
            <nuxt />
          </v-col>
          <v-col cols="12" md="3">
            <!-- ライトサイドバー -->
          </v-col>
        </v-row>
      </v-container>
    </v-main>

    <v-footer
      padless
    >
      <v-card
        flat
        tile
        width="100%"
        class="text-center"
        color="primary"
      >
        <v-card-text>
          <v-btn
            v-for="icon in icons"
            :key="icon.icon"
            class="mx-4 white--text"
            :href="icon.href"
            icon
            fab
            target="_blank"
            rel="noopener noreferrer"
          >
            <v-icon size="24px">
              {{ icon.icon }}
            </v-icon>
          </v-btn>
        </v-card-text>

        <v-divider />

        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} — <strong>&copy;coolbruin</strong>
        </v-card-text>
      </v-card>
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
      ],
      icons: [
        {
          href: 'https://github.com/coolbruin',
          icon: 'fab fa-github'
        },
        {
          href: 'https://twitter.com/coolbruin',
          icon: 'fab fa-twitter'
        },
        {
          href: 'https://bruinkuma.hatenablog.com',
          icon: 'fas fa-blog'
        }
      ]
    }
  },
  mounted () {
    const theme = localStorage.getItem('useDarkTheme')
    if (theme) {
      if (theme === 'true') {
        this.$vuetify.theme.dark = true
      } else {
        this.$vuetify.theme.dark = false
      }
    }
  },
  methods: {
    changeTheme () {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark
      localStorage.setItem('useDarkTheme', this.$vuetify.theme.dark.toString())
      // eslint-disable-next-line vue/no-mutating-props
      this.goDark = !this.goDark
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
