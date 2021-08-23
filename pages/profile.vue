<template>
  <div class="d-flex justify-center">
    <v-card class="mb-5" width="1200">
      <v-img
        contain
        max-height="400"
        class="mt-5"
        :src="imageUrl"
      />

      <!-- names -->
      <div class="d-flex flex-column align-center">
        <div class="ma-5 text-h3 font-weight-thin">
          Takagi Ayano
        </div>
        <div class="ma-5 text-h2 font-weight-thin">
          鷹木 彩乃
        </div>
        <v-btn
          text
          href="https://twitter.com/toxicA643"
          target="_blank"
        >
          <fa :icon="faTwitter"/>
          <span>Twitter</span>
        </v-btn>

        <!-- 紹介文 -->
        <div style="margin-top: 100px; max-width: 700px;">
          <p class="text-h5 font-weight-light">
            {{ description }}
          </p>
        </div>

        <!-- 実績 -->
        <div class="text-h5 mx-auto mb-4" style="margin-top: 100px">
          Performance
        </div>
        <div class="mb-10" style="width: 300px;">
          <template v-for="(perform, i) in performances">
            <performance-item
              :key="i"
              :perform="perform"
            />
          </template>
        </div>
      </div>
    </v-card>
  </div>
</template>

<script>
import { Vue, Component } from 'vue-property-decorator'
import { faTwitter } from '@fortawesome/free-brands-svg-icons'
import client from '@/plugins/contentful'
import PerformanceItem from '@/components/performance-item.vue'

@Component({
  components:{
    PerformanceItem,
  }
})
export default class GarallyItem extends Vue {
  performances = []
  description = ""
  imageUrl = ""

  created() {
    Promise.all([
      client.getEntries({ content_type: "performance" }),
      client.getEntries({ content_type: "profile" })
    ]).then(([performances, profiles]) => {

      performances.items.forEach(perform => {
        const p = perform

        this.performances.push({
          performedAt: p.fields.performedAt,
          title: p.fields.title,
        })
      })

      const profile = profiles.items[0]
      const p = profile.fields
      this.description = p.description
      this.imageUrl = p.faceImage.fields.file.url

    }).catch(console.error)
  }

  get faTwitter() {
    return faTwitter
  }
}

// export default {
//   asyncData({env}) {
//     return Promise.all([
//       client.getEntries({ content_type: "performance" }),
//       client.getEntries({ content_type: "profile" })
//     ]).then(([performances, profiles]) => {
//       return {
//         performances: performances.items,
//         profile: profiles.items[0],
//       }
//     }).catch(console.error)
//   },
//   computed: {
//     faTwitter() {
//       return faTwitter
//     }
//   },
// }
</script>
