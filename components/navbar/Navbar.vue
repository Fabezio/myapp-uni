<template lang="pug">
v-app-bar(app dark="handleTheme" flat tile)
  v-toolbar(flat padless tile).py-n2
    Brand(label='Fabezio')
    Navlinks
    Navlinks(url='skills', label='Compétences' icon='text-box-check')
    Navlinks(url='contact', label='Contactez-moi!' icon='pen')
    v-spacer
    v-btn(@click='toggleTheme', color='info') {{theme}}
    v-chip(v-if="" @click="showClock")
      v-avatar
        v-icon mdi-clock
    v-chip(@click="showClock") {{hour}}:{{min}}


</template>

<script>
export default {
  data() {
    return {
      theme: 'sombre',
      min: new Date().getMinutes(),
      hour: new Date().getHours()
    }
  },
  methods: {
    handleTheme() {
      this.hour >= 6 && this.hour < 22
        ? (this.$vuetify.theme.dark = false)
        : (this.$vuetify.theme.dark = true)
    },
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
