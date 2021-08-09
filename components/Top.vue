<template>
  <div id="top">
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
    </v-layout>
  </div>
</template>

<script>
export default {
  data () {
    return {
    }
  }
}
</script>
<style>
</style>
