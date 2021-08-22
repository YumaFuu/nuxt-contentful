<template>
  <div class="d-flex justify-center flex-wrap">
    <template v-for="(post, i) in posts">
      <garally-item
        :key="i"
        :post="post"
        class="mx-2 mt-4"
      />
    </template>
  </div>
</template>

<script>
import { Vue, Component } from 'vue-property-decorator'
import client from '@/plugins/contentful'

import GarallyItem from '@/components/garally-item.vue'

@Component({
  components: {
    GarallyItem,
  },
})
export default class Garally extends Vue {
  posts = []

  created() {
    client.getEntries({ content_type: 'profile' }).then((profiles) => {
      const profile = profiles.items[0]
      this.src = profile.fields.mainImage.fields.file.url
    })
    client
      .getEntries({
        content_type: 'post',
        order: 'fields.order',
      })
      .then((entries) => {
        entries.items.forEach((post) => {
          const p = {
            src: post.fields.image.fields.file.url,
            title: post.fields.title,
            createdAt: post.fields.createdAt,
            size: post.fields.size,
            description: post.fields.description,
          }

          this.posts.push(p)
        })
      })
      .catch(console.error)
  }
}
</script>
