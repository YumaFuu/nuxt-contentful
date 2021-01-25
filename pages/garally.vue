<template>
  <v-row
    justify="center"
    align="center"
    >
    <v-col
      cols="12"
      v-for="item in posts"
      :key="item.id"
    >
      <v-card
        max-width="450"
        class="mx-auto"
        >
      <v-img
        position="center"
        :src="item.fields.image.fields.file.url"
      >
      </v-img>
      <v-card-title class="headline">
        {{ item.fields.title }}
      </v-card-title>
      <v-card-text>
        <p>{{ item.fields.createdAt }}</p>
        <p>{{ item.fields.size }}</p>
        <p class="font-weight-medium">
          {{ item.fields.description }}
        </p>
      </v-card-text>
      </v-card>
    </v-col>
  </v-row>

</template>

<script>
import contentfulClient from '@/plugins/contentful'
const baseUrl = "https://images.ctfassets.net"

export default {
  asyncData() {
    return contentfulClient
      .getEntries({
        content_type: "post",
        order: "fields.order",
      })
      .then((entries) => {
        return {
          posts: entries.items
        }
      }
    )
    .catch(console.error)
  },
}
</script>
