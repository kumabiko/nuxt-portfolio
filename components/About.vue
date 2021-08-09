<template>
  <div id="profile">
    <div class="py-12" />

    <v-container class="text-center">
      <h2 class="display-2 font-weight-bold mb-3">
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

      <v-responsive
        class="mx-auto title font-weight-light mb-8"
        max-width="720"
      >
        フロントエンドエンジニア。都内のIT企業勤務。<br>
        金融系SEから自社開発サービスのWebエンジニアに転職。<br>
        サービス開発やUI/UXに興味があり、現在勉強中。
      </v-responsive>

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
