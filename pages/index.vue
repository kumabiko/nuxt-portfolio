<template>
  <div>
    <Top />
    <v-divider />
    <About />
  </div>
</template>

<script>
import Top from '~/components/Top.vue'
import About from '~/components/About.vue'

export default {
  components: {
    Top,
    About
  }
}
</script>
