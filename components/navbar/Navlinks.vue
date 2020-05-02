<template lang="pug">
div
  nuxt-link.route(:to='`/${url}`')
    v-chip.mr-2(medium rounded)
      v-avatar.avatar.ml-n1(size='36' color='')
        v-icon(size="16") mdi-{{icon}}
      span.ml-1 {{label}}


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
    },
    icon: {
      type: String,
      default: 'home'
    }
  }
}
</script>

<style lang="stylus" scoped>
.nuxt-link-exact-active .avatar
  background-color teal !important
</style>
