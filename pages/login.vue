<template lang="pug">
section.container
  div
    h1.title Welcome to Summoners Rift
  br
  form.login-form
    div
      LoginForm
    br
    .col-center
      a#auth-button.button.color-aquamarin.text-white ログイン
</template>

<script>
  import LoginForm from '~/components/LoginForm.vue'

  export default {
    components: {
      LoginForm
    }
  }
</script>

<style lang="stylus">
.title
  text-align center

.color-aquamarin
  background-color #66cdaa

.col-center
  text-align center

.text-white
  color #ffffff

.login-form
  text-align center
</style>
