<template>
  <div>
    <h1 data-computed>{{ computedMsg }}</h1>
    <h2 data-props>{{ msg }}</h2>
    <h3 data-methods>{{ dataText }}</h3>
    <button @click="changeMessage" />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component'
@Options({
  props: {
    msg: String
  }
})
export default class ClassComponent extends Vue {
  dataText: string = ''
  get computedMsg(): string {
    return `Message: ${(this.$props as any).msg}`
  }

  changeMessage(): void {
    this.dataText = 'Updated'
  }
}
</script>
