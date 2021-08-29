<template>
  <div id="profile">
    <div class="py-12" />

    <v-container class="text-center">
      <h2 class="display-1 font-weight-bold mb-3">
        ABOUT ME
      </h2>

      <v-responsive
        class="mx-auto mb-8"
        width="56"
      >
        <v-divider class="mb-1" />

        <v-divider />
      </v-responsive>

      <v-avatar
        class="elevation-12 mb-12"
        size="128"
      >
        <v-img src="/image/bear_icon.png" />
      </v-avatar>

      <h3 class="headline mb-4">
        <span>くまろー</span>
      </h3>

      <div>
        <p>
          社会人二年目のフロントエンドエンジニア<br>
          金融系のSEから自社サービス開発のWebエンジニアに転職<br>
          デザインとアイデアを考える事が好きです。
        </p>
      </div>

      <div />

      <!-- <v-btn
        color="grey"
        href="https://vuetifyjs.com"
        outlined
        large
      >
        <span class="grey--text text--darken-1 font-weight-bold">
          Vuetify Documentation
        </span>
      </v-btn> -->
    </v-container>
  </div>
</template>
<script>
export default {
  data: () => ({
  })
}
</script>
