<template>
  <div id="top">
    <v-container fluid>
      <v-layout column justify-center align-center class="mt-4 pt-2">
        <v-card
          width="100vw"
        >
          <v-img
            class="white--text align-center text-center font-italic"
            :class="{'headline': $vuetify.breakpoint. smAndDown, 'display-1': $vuetify.breakpoint. mdAndUp}"
            src="/image/hans-jurgen-mager-qQWV91TTBrE-unsplash.jpg"
          >
            <p>Hello World!</p>
          </v-img>
        </v-card>
        <v-card-actions class="hidden-sm-and-down">
          <v-btn
            v-for="icon in icons"
            :key="icon.icon"
            fab
            dark
            outlined
            color="indigo"
            :href="icon.href"
            target="_blank"
          >
            <v-icon dark>
              {{ icon.icon }}
            </v-icon>
          </v-btn>
        </v-card-actions>

        <v-card-actions class="hidden-md-and-up justify-center">
          <v-btn
            v-for="icon in icons"
            :key="icon.icon"
            fab
            dark
            outlined
            color="indigo"
            :href="icon.href"
            target="_blank"
          >
            <v-icon dark>
              {{ icon.icon }}
            </v-icon>
          </v-btn>
        </v-card-actions>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
export default {
  data () {
    return {
      icons: [
        {
          href: 'https://github.com/39O44O',
          icon: 'fab fa-github'
        },
        {
          href: 'https://twitter.com/BruinKuma',
          icon: 'fab fa-twitter'
        },
        {
          href: 'https://bruinkuma.hatenablog.com',
          icon: 'fas fa-blog'
        }
      ]
    }
  }
}
</script>
<style>
</style>
