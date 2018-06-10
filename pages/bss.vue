<template lang="pug">
div.content
  div.article
    Article(
      v-for="(article, index) in articles"
      v-bind:article="article"
      v-bind:index="index"
      v-bind:key="index")
  div.submit.card
    SubmitForm

</template>

<script>
import Article from '~/components/bss/Article.vue'
import SubmitForm from '~/components/bss/SubmitForm.vue'

export default {
  components: {
    Article,
    SubmitForm
  },
  name: 'articles',
  data() {
    return {
      articles:[
        { name: "Leb Deceiver", id: "@sunlight", img: '/ffxiv_dragon_knight.png', content: '零式アレキで燃え尽きました。。', datetime: '2018/06/05 15:06:52'},
        { name: "Chica Bonita", id: "@sando8307", img: '/ffxiv_minstrel.png', content: '女子高生犯すのが日課！', datetime: '2018/06/05 15:07:16'},
        { name: "Stjp Mighty", id: "@kaaaamiken381", img: '/ffxiv_knight.png', content: 'ズルワーン討伐戦中に食べるカップラーメンうまっww', datetime: '2018/06/05 15:08:23'},

      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
.article  {
  display: flex;
  flex-direction: column;
  min-height: 78vh;
}

.submit
  margin-top: auto;
  padding-top: 10px;
  padding-right: 10px;
  padding-bottom: 10px;
</style>
