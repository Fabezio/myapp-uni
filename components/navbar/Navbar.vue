<template lang="pug">
v-app-bar(app dark="handleTheme" flat tile)
  v-toolbar(flat padless tile).py-n2
    Brand(label='Fabezio')
    Navlinks
    Navlinks(url='skills', label='Compétences' icon='text-box-check')
    Navlinks(url='contact', label='Contactez-moi!' icon='pen')
    v-spacer
    v-btn(@click='toggleTheme', color='info') {{theme}}
    div.timer.ml-2(@click="toggleTimer = !toggleTimer")
      v-avatar(v-if="!toggleTimer" )
        v-icon mdi-clock
      span(v-else) {{hour < 10 ? '0' : '' + hour}}:{{min}}

</template>

<script>
export default {
  data() {
    return {
      theme: 'sombre',
      hour: new Date().getHours(),
      min: new Date().getMinutes(),
      toggleTimer: false
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
.timer
  width 5rem
</style>
