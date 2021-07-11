<template>
  <div id="top">
    <v-container fluid>
      <v-card
        width="100vw"
      >
        <v-img
          class="white--text align-center text-center font-italic"
          :class="{'headline': $vuetify.breakpoint. smAndDown, 'display-1': $vuetify.breakpoint. mdAndUp}"
          src="/image/hans-jurgen-mager-qQWV91TTBrE-unsplash.jpg"
        >
          <p>Sample Portfolio</p>
        </v-img>
      </v-card>
    </v-container>
  </div>
</template>
