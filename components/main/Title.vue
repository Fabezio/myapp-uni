<template lang="pug">
h1.display-4.my-4.text-center
  | {{label}}
</template>
<script>
export default {
  props: {
    label: {
      type: String,
      default: 'Fabezio'
    }
  }
}
</script>
