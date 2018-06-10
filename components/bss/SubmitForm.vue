<template lang="pug">
article.media
  figure.media-left
    p.image.is-64x64
      img(src="/ffxiv_dragon_knight.png")
      p.users
        | @sunlight
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

}
</script>

<style lang="stylus" scoped>

</style>
