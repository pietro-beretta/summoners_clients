<template lang="pug">
div
  b-field(label="Username")
    b-input.login-text-box(maxlength="30")
  b-field(label="Password")
    b-input.login-text-box(type="password" password-reveal)
</template>

<style lang="stylus">
.login-text-box
  margin 0 auto
  width 300px
</style>
