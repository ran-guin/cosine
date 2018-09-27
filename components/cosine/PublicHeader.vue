<template lang='pug'>
  div.publicHeader
    HEAD
      meta(name='viewport' content='width=device-width, initial-scale=1.0')
      link(rel="shortcut icon" :href='ico')

    span.navbar-left
      img.logo(src='/static/images/cosine.logo.png')
    span.navbar-centre()
    span.navbar-right
      span(v-html="right")
 
      span &nbsp; &nbsp;
 </template>

<script>
export default {
  props: {
    left: {
      type: String,
      default: ''
    },
    right: {
      type: String,
      default: ''
    },
    centre: {
      type: String,
      default: ''
    },
    login: {
      type: Boolean,
      default: true
    }
  },
  data() {
    return {
      ico: '/static/images/icons/cosine.ico'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/*
img.logo {
  max-height: 200px;
}*/
</style>
