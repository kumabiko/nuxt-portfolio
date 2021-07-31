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
        <v-card flat color="transparent" max-width="500">
          <v-card-title primary-title>
            <div>
              <h3 class="headline mb-0">
                <span>About Me</span>
              </h3>
              <div>
                <p>
                  Hello! I'm a front-end enginner.<br>
                  I'm interensted in <span class="indigo--text">Design</span> and <span class="indigo--text">Idea</span>.
                </p>
              </div>
            </div>
          </v-card-title>
        </v-card>
      </v-layout>
    </v-container>
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
