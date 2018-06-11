<template lang="pug">
div.bss
  div.content
    Navbar(v-bind:nav="bss.nav")
    div.article
      Article(
        v-for="(article, index) in bss.articles"
        v-bind:article="article"
        v-bind:index="index"
        v-bind:key="index")
    div.submit.card
      SubmitForm(v-bind:user="bss.user")

</template>

<script>
import Navbar from '~/components/bss/Navbar.vue'
import Article from '~/components/bss/Article.vue'
import SubmitForm from '~/components/bss/SubmitForm.vue'

export default {
  components: {
    Navbar,
    Article,
    SubmitForm
  },
  // name: 'articles',
  data() {
    return {
      bss: {
        nav: {
          title: "Summoners-Clients", img: "/ffxiv_minstrel.png"
        },
        articles:[
          { name: "Leb Deceiver", id: "@sunlight", img: '/ffxiv_dragon_knight.png', content: '零式アレキで燃え尽きました。。', datetime: '2018/06/05 15:06:52'},
          { name: "Chica Bonita", id: "@sando8307", img: '/ffxiv_minstrel.png', content: '友人裏切って零式装備集めるの気持ちいぃぃぃ', datetime: '2018/06/05 15:07:16'},
          { name: "Stjp Mighty", id: "@kaaaamiken381", img: '/ffxiv_knight.png', content: 'ズルワーン討伐戦中に食べるカップラーメンうまっww', datetime: '2018/06/05 15:08:23'},
        ],
        user: {
          id: "@sunlight", img: '/ffxiv_dragon_knight.png'
        }
      }
    }
  }
}
</script>

<style lang="stylus" scoped>

body, .bss, .content
  display: flex;
  flex-direction: column;
  min-height: 100vh;

.article
  margin-top:5px;
  margin-right: 5px;
  margin-left: 5px;
  margin-bottom: 5px;

.submit
  margin-top: auto;
  background-color: #f8f8f8;
  padding-top: 10px;
  padding-right: 10px;
  padding-bottom: 10px;

.bss
  background-color: #f8f8f8;
</style>
