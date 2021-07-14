<template>
  <div id="profile">
    <v-main fluid>
      <v-card
        width="100vw"
      >
        <v-card-title
          class="pa-5 justify-center display-1 font-italic"
        >
          自己紹介
        </v-card-title>

        <v-row
          justify="center"
          align-content="center"
        >
          <v-col
            cols="12"
            sm="5"
            md="5"
            align="center"
          >
            <v-row
              justify="space-around"
              align-content="center"
              style="height:100%"
            >
              <v-avatar
                width="20vW"
                height="auto"
              >
                <img
                  src="/image/bear_icon.png"
                  alt="PROFILE"
                  style="object-fit: cover;"
                >
              </v-avatar>
            </v-row>
          </v-col>
          <v-col
            cols="12"
            sm="6"
            md="6"
          >
            <!-- プロフィール項目の表示 -->
            <v-list>
              <v-list-item
                v-for="profile in profiles"
                :key="profile.content"
              >
                <v-list-item-content>
                  <v-list-item-title><v-icon>mdi-check</v-icon> {{ profile.content }}</v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list>
          </v-col>
        </v-row>
      </v-card>
    </v-main>
  </div>
</template>
<script>
export default {
  data: () => ({
    profiles: [
      { content: '名前' },
      { content: '生年月日' },
      { content: '出身地' },
      { content: '出身大学' },
      { content: '職業' },
      { content: '資格' },
      { content: '趣味' },
      { content: '特技' },
      { content: 'その他' }
    ]
  })
}
</script>
