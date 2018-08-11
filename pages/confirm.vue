<template lang="pug">
section.container
  div
    h1.title 認証番号を入力してください
  br
  form.auth-form
    div.message.is-danger(v-if="errors")
      div.message-body {{ errors }}
    div
      b-field(label="Email")
        b-input.auth-text-box(type="email" v-model="email" @keyup.enter="signUpConfirm" required)
      b-field(label="Confirm Code")
        b-input.auth-text-box(type="text" v-model="code" @keyup.enter="signUpConfirm" required)
    br
    .col-center
      a#auth-button.button.color-aquamarin.text-white(@click="signUpConfirm") 送信
</template>

<script>
import { Auth } from 'aws-amplify'
export default {
  data () {
    return {
      email: this.$store.getters['amplify/username'],
      code: '',
      errors: ''
    }
  },
  methods: {
    signUpConfirm () {
      Auth.confirmSignUp(this.email, this.code)
        .then(data => {
          this.$store.dispatch('amplify/clearUsername')
          this.$router.push('/bbs')
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
