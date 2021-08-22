<template>
  <div class="d-flex justify-center mx-4">
    <v-card
      align="center"
      width="1200"
    >
      <v-img
        contain
        max-width="900"
        max-height="400"
        :src="src"
      />
      <div class="px-4 pt-4 pb-7">
        <div class="ma-5 text-h3 font-weight-thin">
          Takagi Ayano
        </div>
        <div class="ma-5 text-h2 font-weight-thin">
          鷹木 彩乃
        </div>
        <div class="ma-5 text-h4 font-weight-thin">
          works
        </div>
      </div>
    </v-card>
  </div>
</template>

<script>
import { Vue, Component } from 'vue-property-decorator'

import client from '@/plugins/contentful'

@Component
export default class Index extends Vue {
  src = ''

  created() {
    client.getEntries({ content_type: 'profile' }).then((profiles) => {
      const profile = profiles.items[0]
      this.src = profile.fields.mainImage.fields.file.url
    })
  }
}
</script>
