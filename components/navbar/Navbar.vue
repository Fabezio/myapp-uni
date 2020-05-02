<template lang="pug">
v-app-bar(app dark dense flat tile)
  v-toolbar(flat dense padless tile)
    v-toolbar-title.ml-n7.my-1
      nuxt-link(to='/home')
        v-btn(dark color='grey' large).mr-2 Fabezio
    //- v-spacer
    nuxt-link(to="/home")
      v-chip.mr-1(text rounded)
        | Accueil

    nuxt-link(to="/error")
      v-chip.mr-1(text rounded)
        | euh...

    nuxt-link(to="/error")
      v-chip.mr-1(text rounded disabled)
        | inactif


</template>

<script>
export default {
  data() {
    return {
      //
    }
  }
}
</script>

<style lang="stylus" scoped>
//
</style>
