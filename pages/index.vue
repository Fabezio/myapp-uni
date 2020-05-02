<template lang="pug">
v-container.text-center
  Title(label='Bienvenue!')
  v-img.avatar.mx-auto.my-4(src='img/avatars/face_co-400px.png')
  nuxt-link(to='/home')
    v-btn() Entrer
</template>

<script>
// import Logo from '~/components/Logo.vue'
// import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  layout: 'white'
}
</script>

<style lang="stylus" scoped>
.avatar
  width 200px
  height 200xp
</style>
