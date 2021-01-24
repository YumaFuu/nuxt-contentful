<template>
  <v-row justify="center" align="center">
    <v-col>
      <v-card
        class="mx-auto"
        align="center"
        max-width="1200"
        >
        <v-sheet min-height="30"></v-sheet>
        <v-img
          contain
          max-height="400"
          :src="profile.fields.mainImage.fields.file.url"
          >
        </v-img>
          <v-sheet
            tile
            class="px-4 pt-4 pb-3"
            >
            <div class="ma-5 text-h3 font-weight-thin">
              Takagi Ayano
            </div>
            <div class="ma-5 text-h2 font-weight-thin">
              鷹木 彩乃
            </div>
            <div
              class="ma-5 text-h4 font-weight-thin"
              >works</div>
          </v-sheet>
          <v-sheet min-height="100"></v-sheet>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import contentfulClient from '@/plugins/contentful'
const client = contentfulClient

export default {
  asyncData() {
    return client
      .getEntries({ content_type: "profile" })
      .then((profiles) => {
        console.log("000000000");
        console.log(profiles.items[0]);
        return {
          profile: profiles.items[0]
        }
      })
      .catch(console.error)
  }
}
</script>
