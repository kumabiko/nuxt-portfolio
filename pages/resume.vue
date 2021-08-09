<template>
  <div id="profile">
    <v-container>
      <h2
        class="pa-5 text-center"
      >
        経歴
      </h2>

      <v-timeline
        :dense="$vuetify.breakpoint.smAndDown"
      >
        <v-timeline-item
          v-for="(year, i) in years"
          :key="i"
          :color="year.color"
          :icon="year.icon"
          fill-dot
        >
          <template #opposite>
            <span
              :class="`headline font-weight-bold ${year.color}--text`"
              v-text="year.year"
            />
          </template>
          <v-card class="rounded-xl">
            <v-card-title>
              <span
                justify-center
                :class="`${year.color}--text`"
              >
                {{ year.title }}
              </span>
            </v-card-title>
            <v-card-text>
              {{ year.content }}
            </v-card-text>
          </v-card>
        </v-timeline-item>
      </v-timeline>
    </v-container>
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
    ],
    years: [
      {
        color: 'primary',
        icon: 'mdi-school',
        year: '2020',
        title: '立命館大学経済学部 卒業',
        content: ''
      },
      {
        color: 'primary',
        icon: 'mdi-office-building',
        year: '2020',
        title: '某SIer システムエンジニア',
        content: '金融系の大規模システムの保守・運用の業務に従事'
      },
      {
        color: 'primary',
        icon: 'mdi-office-building-outline',
        year: '2021',
        title: '某IT企業 フロントエンジニア',
        content: '自社開発サービスの事業部で、フロントエンドエンジニアとして従事'
      },
      {
        color: 'primary',
        icon: 'mdi-calendar-question',
        year: '20✖️✖️',
        title: 'デザインエンジニア',
        content: 'エンジニアリングとデザインの両立を図る働き方を目指しています。'
      }
    ]
  })
}
</script>
