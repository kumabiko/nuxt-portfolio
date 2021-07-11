<template>
  <div>
    <Top />
    <v-divider />
    <Profile />
    <Work />
    <Contact />
  </div>
</template>

<script>
import Top from '~/components/Top.vue'
import Profile from '~/components/Profile.vue'
import Work from '~/components/Work.vue'
import Contact from '~/components/Contact.vue'

export default {
  components: {
    Top,
    Profile,
    Work,
    Contact
  }
}
</script>
