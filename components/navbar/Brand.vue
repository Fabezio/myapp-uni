<template lang="pug">
v-toolbar-title.ml-n5.pt-2.mt-n1
  nuxt-link(to='to')
    v-btn(dark color='grey' large).mr-3 Fabezio
</template>

<script>
export default {
  props: {
    to: {
      type: String,
      default: '/home'
    },
    label: {
      type: String,
      default: ''
    }
  }
}
</script>

<style lang="stylus" scoped></style>
