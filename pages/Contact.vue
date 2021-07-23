<template>
  <div id="contact">
    <v-container fluid>
      <v-card
        width="100vw"
      >
        <iframe
          :src="src"
          width="100%"
          height="750px"
          frameborder="0"
          marginheight="0"
          marginwidth="0"
        >読み込んでいます…
        </iframe>
      </v-card>
    </v-container>
  </div>
</template>
<script>
export default {
  data: () => ({
    src: 'https://docs.google.com/forms/d/e/1FAIpQLSeXLujAHlD744tUN4m-y-zs_mnoEnE88Gg0Hd2tSQlrr0M1Dw/viewform?embedded=true'
  })

}
</script>
