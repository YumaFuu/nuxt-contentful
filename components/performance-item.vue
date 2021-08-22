<template>
  <div class="d-flex">
    <div class="text-h6 font-weight-light mr-4">
      {{ performedAt }}
    </div>
    <div class="text-h6 font-weight-light">
      {{ title }}
    </div>
  </div>
</template>
<script>
import { Vue, Component, Prop } from 'vue-property-decorator'

@Component
export default class PerformanceItem extends Vue {
  @Prop() perform

  get title() {
    return this.perform?.title
  }

  get performedAt() {
    return this.perform?.performedAt
  }
}
</script>
