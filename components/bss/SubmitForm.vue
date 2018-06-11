<template lang="pug">
article.media
  figure.media-left
    p.image.is-64x64
      img(:src="user.img")
      p.users
        | {{user.id}}
  div.media-content
    div.field
      p.control
        textarea.textarea(placeholder="Add a comment...")
    nav.level
      div.level-left
        div.level-item
          a.button.is-info
            | Submit

</template>

<script>
export default {
  props: ['user']
}
</script>

<style lang="stylus" scoped>

</style>
