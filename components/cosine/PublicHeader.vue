<template lang='pug'>
  div.publicHeader
    HEAD
      meta(name='viewport' content='width=device-width, initial-scale=1.0')
      link(rel="shortcut icon" :href='ico')
    div.col-xs-4.info-logo
      img.logo(src='~/static/images/cosine.logo.png' alt='cosine.logo.png')
    // div.col-xs-8.info-logo.myMenu
    //   span(v-for='link in links') 
    //     span.menuItem(v-for='key, label in link')
    //       nuxt-link(:to='key') {{label}} &nbsp; &nbsp;
 </template>

<script>
import CustomMenu from './../Standard/Menu'

export default {
  components: {
    CustomMenu
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
    onSelect: {
      type: Function,
      default() {
        return null
      }
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
  },
  computed: {
    onClick: function(el) {
      if (this.onSelect) {
        console.log('picked...')
        return this.onSelect
      } else {
        console.log('no click function supplied')
        return null
      }
    }
  }
}
</script>

<style scoped lang="sass">
img.logo
  max-height: 10rem;
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
</style>
