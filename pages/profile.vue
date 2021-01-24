<template>
  <v-row justify="center" align="center">
    <v-col>
      <v-card
        class="mx-auto"
        max-width="1200"
        >
        <v-sheet min-height="20"></v-sheet>
        <v-col
          cols="8"
          offset="2"
          align="center"
          max-width="500"
          >
          <v-img
            contain
            max-height="400"
            :src="profile.fields.faceImage.fields.file.url"
          ></v-img>
        </v-col>
        <v-col
            cols="12"
            align="center"
            >
            <v-sheet min-height="20"></v-sheet>
            <div class="ma-5 text-h3 font-weight-thin">
              Takagi Ayano
            </div>
            <div class="ma-5 text-h2 font-weight-thin">
              鷹木 彩乃
            </div>
          </v-col>
          <v-col
            align="center"
            >
            <v-btn
              text
              href="https://twitter.com/toxicA643"
              target="_blank"
            >
              <fa :icon="faTwitter"/>
              <span>Twitter</span>
            </v-btn>
          </v-col>
        <v-sheet min-height="100"></v-sheet>
      <v-col
        cols="10"
        offset="1"
        align="center"
        >
        <p class="text-h5 font-weight-light">
         {{ profile.fields.description }}
        </p>
      </v-col>
      <v-sheet min-height="100"></v-sheet>
      <v-row>
        <v-col
          cols="12"
          align="center"
          class="text-h5">
          Performance
        </v-col>
        <v-col
          cols="10"
          offset="1"
          align="left"
          v-for="item in performances"
          :key="item.id"
          >
          <v-row>
            <v-col cols="4">
              <p class="text-h6 font-weight-light" align="right">
                {{ item.fields.performedAt }}
              </p>
            </v-col>
            <v-col cols="8" >
              <p class="text-h6 font-weight-light">
                {{ item.fields.title }}
              </p>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import { faTwitter } from '@fortawesome/free-brands-svg-icons'
import contentfulClient from '@/plugins/contentful'
const client = contentfulClient

export default {
  computed: {
    faTwitter() {
      return faTwitter
    }
  },
  asyncData({env}) {
    return Promise.all([
      client.getEntries({ content_type: "performance" }),
      client.getEntries({ content_type: "profile" })
    ]).then(([performances, profiles]) => {
      return {
        performances: performances.items,
        profile: profiles.items[0],
      }
    }).catch(console.error)
  },
}
</script>
