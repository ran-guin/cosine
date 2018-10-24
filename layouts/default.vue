<template lang='pug'>
  div.page
    div.header.myHeader
      PublicHeader(:page='page' :tabs='links' :onTab='activate')

    div.subheader.subheader1
      span &nbsp;
    div.body.myBody
      div.background-image
      nuxt
    div.footer.myFooter
      PublicFooter()
  </div>
</template>

<script>
import PublicHeader from './../components/cosine/PublicHeader'
import PublicFooter from '~/components/cosine/PublicFooter'
import Tabs from '~/components/Standard/Tabs'
export default {
  name: 'Hello',
  components: {
    PublicHeader,
    PublicFooter
  },
  data() {
    return {
      page: 'us',
      links: [
        { About: 'mission' },
        { Expertise: 'us' },
        // { Demos: 'demos' },
        { Projects: 'projects' },
        // { Staff: 'staff' },
        { Contact: 'contact' }
      ],
      tabs: ['About', 'Expertise', 'Projects', 'Contact']
    }
  },
  computed: {
    pickClass(val) {
      if (this.page === val) {
        return 'onPage'
      } else {
        return 'offPage'
      }
    }
  },
  methods: {
    activate(layer) {
      console.log('activate ' + layer + ' page')
      this.page = layer
    }
  }
}
</script>

<style lang="sass">
html
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 1rem;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;

*,
*:before,
*:after
  box-sizing: border-box;
  margin: 0;

.button--green
  display: inline-block;
  border-radius: 0.5rem;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 1rem 3rem;

.button--green:hover
  color: #fff;
  background-color: #3b8070;

.button--grey
  display: inline-block;
  border-radius: 0.5rem;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 1rem 3rem;
  margin-left: 1.5rem;

.button--grey:hover
  color: #fff;
  background-color: #35495e;

/*** Customize Header / Footer Settings: ***/
$header-background-colour: white;
$default-padding: 2rem 3rem;
$header-colour: lightgrey;

$header-font-size: 4rem;
$footer-font-size: 3rem;

$footer-colour: black;
$footer-background-colour: turquoise;

$subheader-background-colour: turquoise;

$body-background-colour: #ddd;
$body-colour: black;

$min-height: 30rem;
$header-height: 15rem;
$subheader-height: 1rem;
$footer-height: 6rem;

// $min-height: 500px;
// $header-height: 100px;
// $subheader-height: 0px;
// $footer-height: 100px;

.page
  /*margin-top: -20px;*/
  height: 100%;
  width: 100%;

.myHeader
  color: $header-colour;
  background-color: $header-background-colour;
  padding: 0px;
  width: 100%;
  height: $header-height;

.subheader
  color: white;
  background-color: $subheader-background-colour;
  height: $subheader-height;
  width: 100%;
  z-index: 1;
  text-align: center;
  padding: 1rem;

.myFooter
  background-color: $footer-background-colour;
  padding: $default-padding;
  width: 100%;
  padding-left: 5rem;
  padding-right: 5rem;
  padding-top: 1rem;
  padding-bottom: 1rem;
  height: $footer-height;
  font-size: 1.5rem;

a
  color: black;
  font-weight: normal;
  text-decoration: none;

a:hover
  color: black;
  font-weight: bold;
  text-decoration: none;

.html
  min-height: calc(#{$min-height} + #{$header-height} + #{$subheader-height} + #{$footer-height})

.myBody
  font-size: 1rem;
  min-height: $min-height;
  background-color: transparent;

.background-image
  background: url('./../static/images/cosine/animated_sine.gif') no-repeat center fixed;
  position: absolute;
  top: 0;
  left: 0;
  background-size: cover;
  height: 100%;
  width: 100%;
  opacity: 0.1;
  z-index: -1;

@media screen and (min-height: $min-height + $header-height + $subheader-height + $footer-height)
  .myBody
    min-height: calc(100vh - #{$header-height} - #{$subheader-height} - #{$footer-height});
    // min-height: calc(100vh - $min-height - $header-height - $subheader-height - $footer-height);
    // background-color: #ddd; 

@media screen and (max-width: 767px)
  .myHeader
    height: auto;
    min-height: 4rem;
  .subheader
    height: auto;

.overlay
  position: absolute;

.navbar-centre
    position: absolute;
    width: 100%;
    left: 0;
    text-align: center;
    margin: 0 auto;

// .onPage
//   color: black;
//   // font-weight: bold;
//   // background-color: grey !important;

// .onPage:hover
//   color: black;
//   // background-color: grey !important;

// .offPage
//   // background-color: grey !important;
//   color: grey;

// .offPage:hover
//   // background-color: darkgrey !important;
//   color: black;

.menuItem
  font-size: 2rem;

.heading
  color: blue;

hr
  border-top: 2px solid grey

.myMenu
  padding: 2rem;

// wide version first
.flex-container
  display: flex;
  flex-direction: row;

.flex-item
  width: 25%
  flex-direction: column;
  padding-left: 1rem;
  padding-right: 1rem;
  border: 0px;

.menuItem
  width: 100%
  padding-left: 1rem;
  padding-right: 1rem;
  text-decoration: none;
  a
    color: #333
    text-decoration: none;
  a:focus
    color: black;
    font-weight: bold;
  a:hover
    color: red;
    font-weight: bold;
  .onPage
    color: black;
    font-weight: bold;
    font-size: 2rem;
  .offPage
    color: #333
    font-size: 2rem;

</style>
