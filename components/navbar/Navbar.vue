<template lang="pug">
v-app-bar(app dark flat tile)
  v-toolbar(flat padless tile).py-n2
    Brand(label='Fabezio')
    Navlinks
    Navlinks(url='skills', label='Compétences' icon='text-box-check')
    Navlinks(url='contact', label='Contactez-moi!' icon='pen')
    v-spacer
    <v-btn @click="toggleTheme" color="info">{{theme}}</v-btn>


</template>

<script>
export default {
  data() {
    return {
      // dark: this.$vuetify.theme.dark
      theme: 'sombre'
    }
  },
  methods: {
    toggleTheme() {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark
      !this.$vuetify.theme.dark
        ? (this.theme = 'clair')
        : (this.theme = 'sombre')
    }
  }
}
</script>

<style lang="stylus" scoped>
//
</style>
