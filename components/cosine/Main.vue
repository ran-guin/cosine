<template lang='pug'>
  div.page
    div.subheader.overlay
      b Menu...
      CustomMenu(:links='links' type='function' :onClick="activate" :active="active_block")
    div.body.container
      <!-- img.bg -->
      div
        span(v-if="active_block==='staff'")
          Staff()
        span(v-else-if="active_block==='mission'")
          Mission()
        span(v-else)
          h3 {{active_block}} ?
</template>

<script>
import Staff from './Staff'
import Mission from './Mission'
import CustomMenu from './../Standard/Menu'

export default {
  name: 'Hello',
  components: {
    // Block,
    CustomMenu,
    Staff,
    Mission
    // Contact,
    // Us,
    // Demos,
    // Projects
    // Tools
  },
  data() {
    return {
      // ################## Add Link List Below for Testing ######################
      // links: ['Mission', 'Staff', 'What We Do', 'Active Projects', 'Tools', 'Mail'],
      links: [
        { Mission: 'mission' },
        { Staff: 'staff' },
        { Expertise: 'us' },
        { Demos: 'demos' },
        { Contact: 'contact' },
        { Projects: 'projects' }
      ],
      icons: { Staff: 'user', Mail: 'mail' },
      active_block: 'mission'
    }
  },
  computed: {
    content: function() {
      if (this.block_content && this.block_content[this.active_block]) {
        return this.block_content[this.active_block]
      } else {
        return this.active_block + 'content...'
      }
    }
  },
  methods: {
    activate(layer) {
      console.log('activate ' + layer)
      this.active_block = layer
    }
  }
}
</script>

<style>
/*** Customize Header / Footer Settings: ***/
// $header-height: 160px;
// $header-background-colour: #fff;
// $header-padding: 10px 30px;

// $subheader-height: 50px;
// $subheader-background-colour: #39a;

// $footer-height: 70px;
// $footer-colour: black;
// $footer-background-colour: #39a;

// $body-colour: black;

.page {
  /*margin-top: -20px;*/
  height: 100%;
  width: 100%;
}

.header {
  height: $header-height;
  // background-color: $header-background-colour;
  // padding: $header-padding;
  border-bottom: solid black 1px;
}
.footer {
  // background-color: $footer-background-colour;
  // color: $footer-colour;
  // height: $footer-height;
  width: 100%;

  padding-left: 40px;
  padding-right: 40px;
  padding-top: 15px;
  padding-bottom: 15px;
}

.subheader {
  // background-color: $subheader-background-colour;
  color: white;
  // height: $subheader-height;
  width: 100%;
  z-index: 10000;
}

.body {
  // padding-top: $subheader-height;
  // min-height: calc(100vh - #{$header-height} - #{$footer-height});
  // color: $body-colour;
  z-index: 10000;
  border-top: black 1px;
}

img.bg {
  z-index: -1;
  /* Set rules to fill background */
  min-height: 100%;
  /*min-width: 1024px;*/
  /*background-image: url("/static/images/teapour.jpeg");*/
  /* Center and scale the image nicely */
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;

  /*background-color: rgba(255, 255, 0, 0.3);*/

  z-index: 0;
  opacity: 20%;

  /* Set up proportionate scaling */
  width: 100%;
  height: auto;

  /* Set up positioning */
  position: fixed;
  // top: calc(#{$header-height});
  left: 0;
}

@media screen and (max-width: 1024px) {
  /* Specific to this particular image */
  img.bg {
    left: 50%;
    /*margin-left: -512px;   /* 50% */
  }
}

.overlay {
  position: absolute;
}

.navbar-centre {
  position: absolute;
  width: 100%;
  left: 0;
  text-align: center;
  margin: 0 auto;
}

img.logo {
  max-height: 140px;
}
img.logo-s {
  max-height: 70px;
  margin-top: -15px;
  padding-right: 50px;
}
img.logo-xs {
  max-height: 20px;
}
</style>
