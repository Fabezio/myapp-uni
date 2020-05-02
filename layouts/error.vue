<template lang="pug">
v-container

  v-alert.text-center(v-if='error.statusCode === 404' type='error')
    h1 {{ pageNotFound }}
  v-alert.text-center(v-else type='warning')
    h1 {{ otherError }}
  nuxt-link.float-right(to='/home')
    | Retour à l'accueil

</template>

<script>
export default {
  layout: 'white',
  props: {
    error: {
      type: Object,
      default: null
    }
  },
  data() {
    return {
      pageNotFound: '404 - Page non trouvée',
      otherError: 'Une erreur st survenue'
    }
  },
  head() {
    const title =
      this.error.statusCode === 404 ? this.pageNotFound : this.otherError
    return {
      title
    }
  }
}
</script>

<style scoped>
h1 {
  font-size: 20px;
}
</style>
