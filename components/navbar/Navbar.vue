<template lang="pug">
v-app-bar(app dark flat tile)
  v-toolbar(flat padless tile).py-n2
    Brand(label='Fabezio')
    //- v-spacer
    Navlinks
    Navlinks(url='skills', label='Compétences')

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
