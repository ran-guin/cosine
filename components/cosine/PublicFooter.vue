<template lang='pug'>
  div.publicFooter
    span.navbar-left
      span(v-html="left")
      <!-- img.logo(src='/static/images/cosine.logo.png')  -->
      a(href='/')
        span.acronym
          b &nbsp; C
          span ommunity
          b &nbsp; O
          span riented
          b &nbsp; S
          span oftware
          b &nbsp; I
          span nnovation
          b &nbsp; N
          span etwork
          span &nbsp; &nbsp;
          span &nbsp; &nbsp;
    span.navbar-centre
      span(v-html="centre")
    span.navbar-right
      span(v-html="right")
      a(href="mailto:info@cosine.org?Subject=webpage%20contact") Contact Us

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
    }
  },
  // template: require('./main.pug'),
  data() {
    return {}
  }
}
</script>

<style scoped>
.publicFooter {
  padding: 2rem;
  font-size: 1rem;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  /* margin: 0 10px; */
}

span a {
  color: #222;
}
span a:hover {
  color: #000;
  font-weight: bold;
}
</style>
