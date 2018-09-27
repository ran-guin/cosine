<template lang='pug'>
  div.container
    p &nbsp;
    p &nbsp;
    ul
      li.col-md-2(v-for="link in links")
        a(v-if='link.url' :href='link.url' target="_blank")
          h4(data-tooltip :title='link.description') {{link.name}}
          br
          img(:src="link.img" height='40px')        
        router-link(v-else :to="{name: link.name}" target="_blank")
          h4(data-tooltip :title='link.description') {{link.name}}
          br
          img(:src="link.img" height='40px')
</template>

<script>
// var links = ['Ovid', 'T4U', 'Cosine', 'Sparc'] // 'Main', 'User', 'Login',

export default {
  name: 'Hello',
  data() {
    return {
      msg: 'Welcome to My Vue.js App',
      // ################## Add Link List Below for Testing ######################
      links: [
        {
          name: 'Ovid',
          img: '/static/images/needleIcon.png',
          description: 'Online Vaccination & Immunization Databse'
        },
        {
          name: 'Sparc',
          img: '/static/images/cvenn.gif',
          description: 'Social Platform Affecting Real Connections'
        },
        {
          name: 'UTM',
          img: '/static/images/utm.png',
          description: 'Universal Touring Machine'
        },
        {
          name: 'T4U',
          img: '/static/images/teacup.png',
          description: 'Sample Online Retail Website'
        },
        {
          name: 'LITMUS',
          img: '/static/images/litmus.png',
          description: 'Laboratory Information Management System',
          url: 'http://litmus-a1.herokuapp.com/'
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
