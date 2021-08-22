<template>
  <v-card width="450" class="mx-6">
    <v-img position="center" :src="src" />

    <v-card-title class="headline">
      {{ title }}
    </v-card-title>
    <v-card-text>
      <p>{{ createdAt }}</p>
      <p>{{ size }}</p>
      <p class="font-weight-medium">
        {{ description }}
      </p>
    </v-card-text>
  </v-card>
</template>
<script>
import { Vue, Component, Prop } from 'vue-property-decorator'

@Component
export default class GarallyItem extends Vue {
  @Prop() post

  get src() {
    return this.post.src
  }

  get title() {
    return this.post.title
  }

  get createdAt() {
    return this.post.createdAt
  }

  get size() {
    return this.post.size
  }

  get description() {
    return this.post.description
  }
}
</script>
