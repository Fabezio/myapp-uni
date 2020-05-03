<template lang="pug">
div
  Title(label='Contactez-moi!')
  v-lazy
    v-row.mb-10
      v-col.mx-auto(cols="8")

        v-form
          v-text-field(v-model='username' type='text' placeholder='Nom:' dense  )
            v-icon(slot='prepend') mdi-account
          v-text-field(v-model='email' type='email' placeholder='Email:' dense )
            v-icon(slot='prepend') mdi-email
          v-text-field( v-model='phone' type='tel' placeholder='Téléphone:' dense )
            v-icon(slot='prepend') mdi-cellphone-android
          v-textarea( v-model='phone' type='tel' placeholder='Message:' dense solo)
            v-icon(slot='prepend') mdi-keyboard
          v-checkbox(v-model='checkbox' label='je jure avoir dit la vérité')

          v-alert(type='warning' color='grey') Tous les champs sont requis


          // groupe d'actions
          v-btn-toggle.float-right(dense)
            v-btn(@click="addressCheck" type="submit" color="info")
              v-icon mdi-send
              span envoyer
            v-btn(@click="resetForm" color='warning')
              v-icon mdi-autorenew
              span refaire
            v-btn(@click="$router.push(home)" color='error')
              v-icon mdi-close
              span annuler




</template>

<script>
export default {
  data() {
    return {
      errorMessages: '',
      name: null,
      email: null,
      phone: null,
      message: null,
      formHasErrors: false
    }
  },
  computed: {
    form() {
      return {
        name: this.name,
        address: this.address,
        city: this.city,
        state: this.state,
        zip: this.zip,
        country: this.country
      }
    }
  },

  watch: {
    name() {
      this.errorMessages = ''
    }
  },

  methods: {
    addressCheck() {
      this.errorMessages = this.address && !this.name ? "Hey! I'm required" : ''

      return true
    },
    resetForm() {
      this.errorMessages = []
      this.formHasErrors = false

      Object.keys(this.form).forEach((f) => {
        this.$refs[f].reset()
      })
    },
    submit() {
      this.formHasErrors = false

      Object.keys(this.form).forEach((f) => {
        if (!this.form[f]) this.formHasErrors = true

        this.$refs[f].validate(true)
      })
    }
  }
}
</script>

<style lang="stylus" scoped></style>
