<template lang="pug">
nav.navbar.nav(role="navigation" aria-label="main navigation")
    div.navbar-brand
        a.navbar-item(href="/")
            img(:src="nav.img")
            p.title.is-3
              | {{nav.title}}
        a.navbar-burger(role="button" aria-label="menu" aria-expanded="false")
</template>

<script>
export default {
  props: ['nav']
}
</script>

<style lang="stylus" scoped>
.nav
  background-color: #f8f8f8;
</style>
