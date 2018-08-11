<template lang="pug">
section.container
  div
    h1.title 聞いて、感じて、考えて <br> 光の戦士になってお使いよろいく
  br
  form.auth-form
    div.message.is-danger(v-if="errors")
      div.message-body {{ errors }}
    div
      b-field(label="Email" @keyup.enter="signUp")
        b-input.auth-text-box(type="email" v-model="email" required)
      b-field(label="Password" @keyup.enter="signUp")
        b-input.auth-text-box(type="password" v-model="password" minlength="6" password-reveal required)
      b-field(label="Confirm Password")
        b-input.auth-text-box(type="password" v-model="confirmPassword" minlength="6" password-reveal required)
    br
    .col-center
      a#signup-button.button.color-aquamarin.text-white(@click="signUp") ヒカセン登録
</template>

<script>
import { Auth } from 'aws-amplify'

export default {
  data () {
    return {
      email: '',
      password: '',
      confirmPassword: '',
      errors: ''
    }
  },
  methods: {
    signUp () {
      if (this.confirmPassword != this.password) {
        this.$dialog.alert('パスワードが一致しないよ')
      }

      Auth.signUp({
        username: this.email,
        password: this.password,
        attributes: {
          email: this.email
        }
      }).then(data => {
          this.$store.dispatch('amplify/setUsername', this.email)
          this.$router.push('/confirm')
          this.$dialog.alert('もしもし、私だけど・・・')
        })
        .catch(err => this.errors = err)
    }
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
