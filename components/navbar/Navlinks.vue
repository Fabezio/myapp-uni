<template lang="pug">
div
  nuxt-link(:to='`/${url}`')
    v-chip.mr-2(rounded)
      | {{label}}


</template>

<script>
export default {
  props: {
    url: {
      type: String,
      default: 'home'
    },
    label: {
      type: String,
      default: 'Accueil'
    }
  }
}
</script>

<style lang="stylus" scoped></style>
