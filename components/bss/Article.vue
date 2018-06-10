<template lang="pug">
div.users
  div.card
    div.card-content
      div.media
        div.media-left
          figure.image.is-48x48
            img(:src="article.img" alt="Placeholder image")
        div.media-content
          p.title.is-4
            | {{article.name}}
          p.subtitle.is-6
            | {{article.id}}
      div.content
        | {{article.content}}
        br
        time
          | {{article.datetime}}
</template>

<script>
export default {
  props: ['article']
}
</script>

<style lang="stylus" scoped>
</style>
