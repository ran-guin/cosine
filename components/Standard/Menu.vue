<!-- src/components/Standard/Menu.vue

  Usage:

  Modes of operation:

  type = 'url'. (links point to url .. more flexible, but slower)
  *************
  links: [ goHere: '/goHere', maps: 'https/maps.google.ca']
  eg Menu(:links="links")

  type = 'onClick' ... execute onClick (eg switch layers on tab clicks)
  *****************

  predefine:

  links: [ A: 'Acomponent', B: 'Bcomponent'],
  active_block: 'A',

  methods: {
    activate (layer) {
      console.log('activate ' + layer)
      this.active_block = layer
    }
  },

  template:

  Menu(:links="links" :onClick='activate' :active="active_block")

  div(v-for='link in links')
    div(v-if="active_block==='A'")
      AComponent()

-->

<template lang='pug'>
  div
    span
    <!-- div.navbar-left -->
      span
      ul
        span(v-html='prefix') &nbsp; &nbsp;
        li.dropdown(:class="direction" v-for="link in links")
          span(v-if="link.constructor === Object")
            span(v-for="target,label in link")
              span(v-if="target.constructor === Array && type==='url'")
                <!-- Multi-level menus only ...  -->
                a.dropbtn(href="javascript:void(0)") {{label}}
                div.dropdown-content
                  span(v-for="targetN, index in target")
                    span(v-if="targetN.constructor === Object")
                      span(v-for="subUrl,subLabel in targetN")
                          a(:href="subUrl") S: {{subLabel}}
                    span(v-else)
                      router-link(:to="{name: targetN}") {{targetN}}
              span(v-else-if="type==='url'")
                <!-- Standard array of key:value pairs (name: target)  -->
                a(:href="target" target="_blank") {{label}}
              span(v-else-if="onClick")
                span(v-if="active===target")
                  a.active.input-lg(href='#lower' v-on:click='activate(target)') {{label}}
                span(v-else)
                  a.inactive.input-lg(href='#' v-on:click='activate(target)') {{label}}
              span(v-else)
                <!-- Internal links do not need keys -->
                router-link(:to="{name: link}") {{link}}

</template>

<script>
export default {
  props: {
    links: {
      type: Array,
      default() {
        return []
      }
    },
    type: {
      type: String,
      default: 'url'
    },
    prefix: {
      type: String,
      default: ''
    },
    default: {
      type: String,
      default: ''
    },
    onClick: {
      type: Function,
      default() {
        return null
      }
    },
    options: {
      type: Object,
      default() {
        return {}
      }
    },
    direction: {
      type: String,
      default: 'vertical'
    }
  },

  data() {
    return {
      active_block: ''
    }
  },
  computed: {
    active: function() {
      return this.active_block || this.options.default
    }
  },
  methods: {
    activate: function(layer) {
      this.active_block = layer
      console.log('activated ' + this.active_block)
      this.onClick(layer)
    }
  }
}
</script>

<style scoped lang="sass">

$menubgcolor: 'transparent';
$menuColour: '#ccc';
$hoverColour: '#FFF';
$activeColour: '#EEE';

ul
  backgroundColor: $menubgcolor;
  listStyleType: none;
  margin: 0;
  padding: 0;
  overflow: hidden;

li.vertical
  a
    display:block

li 
  a
    display: block;

li.horizontal
  a
    display: inline-block;
a.dropbtn
    display: inline-block;

li 
  a
    color: $menuColour
    padding: 14px 16px;
    text-decoration: none

a
  padding: 14px 16px;

a.dropbtn
  display: block;
  color: $menuColour;
  text-align: center;
  text-decoration: none;

  font-weight: bold;
  color: $hoverColour;


li 
  a:hover
    font-weight: bold;
    color: $hoverColour;

li.dropdown
    display: inline-block
    &hover
      color: $hoverColour
      font-weight: bold;

li.dropdown

div.dropdown-content
    display: none;
    position: absolute;
    background-color: '#f9f9f9';
    min-width: 160px;
    box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
    z-index: 1;
    a
      color: black;
      padding: '12px 16px';
      text-decoration: none;
      display: block;
      text-align: left;
      key: "value";

li.dropdown
  &hover 
    div.dropdown-content
      display: block;

div.navbar-center
    position: absolute;
    width: '100%';
    left: 0;
    text-align: center;
    margin: '0 auto';

a.active
  font-weight: bold;
  color: $activeColour;

a.inactive
  font-weight: normal;
  color: $menuColour;
</style>
