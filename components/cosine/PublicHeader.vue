<template lang='pug'>
  div.publicHeader
    HEAD
      meta(name='viewport' content='width=device-width, initial-scale=1.0')
      link(rel="shortcut icon" :href='ico')
    div.info-header
      div.info-logo
        img.logo(src='~/static/images/cosine/cosine.logo.png' alt='cosine.logo.png')
      div.info-right
        Tabs.tab-header(v-if='tabs' :list='tabs' :onPick='onTab' defaultTab='Expertise')

 </template>

<script>
// import CustomMenu from './../Standard/Menu'
import Tabs from './../Std/nuxtTabs'

export default {
  components: {
    // CustomMenu,
    Tabs
  },
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
    },
    onTab: {
      type: Function,
      default() {
        return null
      }
    },
    tabs: {
      type: Array,
      default: null
    }
  },
  data() {
    return {
      ico: '/static/images/icons/cosine.ico',
      links: [
        { Mission: 'mission' },
        { Staff: 'staff' },
        { Expertise: 'us' },
        // { Demos: 'demos' },
        { Contact: 'contact' },
        { Projects: 'projects' }
      ],
      active_block: 'mission'
    }
  }
}
</script>

<style scoped lang="sass">
img.logo
  max-height: 200px;
  padding: 1rem;

.myMenu
  padding: 3rem;

.menuItem
  padding-left: 1rem;
  padding-right: 1rem;
  a
    color: #333
  a:hover
    color: black;
    text-decoration: none;

.tab-header

.info-header
  width: 100%;
  // height: 60px;
  // color: #666;
  // background-color: white;

.info-logo
  text-align: left;
  vertical-align: top;
  display: inline-block;

.info-left
  padding-left: 5rem;
  text-align: left;
  // color: black;
  display: inline-block;

.info-right
  float: right;
  text-align: right;
  display: inline-block;
  height: 100%;

@media screen and (max-width: 768px)
  .info-left
    display: none;
  .info-logo
    display: none;
</style>
