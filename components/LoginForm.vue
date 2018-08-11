<template lang="pug">
div
  b-field(label="Email")
    b-input.login-text-box(type="email" maxlength="30" v-model="email" @keyup.enter="signIn" required)
  b-field(label="Password")
    b-input.login-text-box(type="password" v-model="password" @keyup.enter="signIn" password-reveal required)
</template>

<style lang="stylus">
.login-text-box
  margin 0 auto
  width 300px
</style>
