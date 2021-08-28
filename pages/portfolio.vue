<template>
  <div id="portfolio">
    <v-container grid-list-xl>
      <h2 class="pa-5 text-center">
        <span>Web</span>
        <span class="primary--text">Portfolio</span>
      </h2>
      <v-layout row justify-center align-center wrap class="mt-4 pt-2">
        <v-dialog
          v-for="project in projects"
          :key="project.title"
          v-model="project.dialog"
          max-width="1000"
        >
          <template v-slot:activator="{ on , attrs }">
            <v-flex
              sm6
              md6
              v-bind="attrs"
              v-on="on"
            >
              <v-card
                hover
                flat
                elevation="2"
                outlined
                color="transparent">
                <v-img
                  :src="project.image"
                  :alt="project.title"
                  height="250"
                />
                <v-card-title primary-title class="justify-center">
                  {{ project.title }}
                </v-card-title>
              </v-card>
            </v-flex>
          </template>
          <!-- モーダルウィンドウ -->
          <v-card
            :loading="loading"
            class="mx-auto"
          >
            <v-img :src="project.image" />
            <v-card class="pa-3">
              <h1 class="mt-5 text-center">
                {{ project.title }}
              </h1>
              <!-- タグ -->
              <v-card-text class="text-center">
                <v-chip
                  v-for="tag in project.tags"
                  :key="tag"
                  color="primary"
                  class="ma-1"
                >
                  {{ tag.tag }}
                </v-chip>
              </v-card-text>

              <v-divider class="mx-4" />

              <v-card-title>概要</v-card-title>
              <v-card-text>
                {{ project.description }}
              </v-card-text>
              <!-- 制作期間 -->
              <v-card-title>制作時期</v-card-title>
              <v-card-text>
                {{ project.year }}
              </v-card-text>

              <v-card-actions>
                <v-btn
                  flat
                  color="primary"
                  :href="project.url"
                  target="_blank"
                  rel="noopener noreferrer"
                >
                  <v-icon left>
                    mdi-desktop-mac
                  </v-icon>Page
                </v-btn>
                <v-spacer />
                <v-btn
                  color="primary"
                  outlined
                  @click="project.dialog = false"
                >
                  <v-icon left>
                    mdi-close
                  </v-icon>Close
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-card>
          <!-- モーダルウィンドウ -->
        </v-dialog>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
export default {
  data () {
    return {
      projects: [
        {
          dialog: false,
          title: 'This Site',
          image: '/image/portfolio/PortfolioSite.png',
          tags: [
            { tag: '#Nuxt.js' },
            { tag: '#Vue.js' },
            { tag: '#Vuetify' },
            { tag: '#Vercel' }
          ],
          description: 'ポートフォリオ用のサイトです。UIデザインを参考にしながら作成しました。Vuetifyでレスポンシブ・ダークテーマに対応しています。',
          year: '2021年7月~8月',
          url: 'https://nuxt-portfolio-lyart.vercel.app/'
        },
        {
          dialog: false,
          title: '製作中',
          image: 'https://placeimg.com/640/480/any',
          tags: [
          ],
          description: '制作中です。',
          year: '',
          url: '#'
        }
      ]
    }
  }
}
</script>
