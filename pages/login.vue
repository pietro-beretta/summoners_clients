<template lang="pug">
section.container
  div
    h1.title Welcome to Summoners Rift
  br
  form.auth-form
    div.message.is-danger(v-if="errors")
      div.message-body {{ errors }}
    div
      b-field(label="Email")
        b-input.auth-text-box(type="email" v-model="email" @keyup.enter="signIn" required)
      b-field(label="Password")
        b-input.auth-text-box(type="password" v-model="password" @keyup.enter="signIn" password-reveal required)
    br
    .col-center
      a#auth-button.button.color-aquamarin.text-white(@click="signIn") ログイン
</template>

<script>
import { Auth } from 'aws-amplify'
import LoginForm from '~/components/LoginForm.vue'

export default {
  components: {
    LoginForm
  },
  data () {
    return {
      email: '',
      password: '',
      errors: ''
    }
  },
  methods: {
    signIn () {
      Auth.signIn(this.email, this.password)
        .then(data => this.$router.push('/bbs'))
        .catch(err => this.errors = err)
    },
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

.auth-form
  text-align center

.auth-text-box
  margin 0 auto
  width 300px
</style>
