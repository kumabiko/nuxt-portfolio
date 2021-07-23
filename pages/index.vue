<template>
  <div>
    <Top />
    <v-divider />
    <Profile />
  </div>
</template>

<script>
import Top from '~/components/Top.vue'
import Profile from '~/components/Profile.vue'

export default {
  components: {
    Top,
    Profile
  }
}
</script>
