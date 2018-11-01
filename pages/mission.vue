<template lang='pug'>
  div.container
    p &nbsp;
    h1 Mission
    hr
    div.col-md-12
      p.text-lg We are a group of software developers and engineers dedicated to the creative design & implementation of free or low cost web applications for community benefit and public service. 
      div.col-md-6(v-for="m in mission")
        h2 {{m.name}}
        p.text-lg
          ul
            li(v-for="item in m.list") {{item}}
</template>

<script>
export default {
  name: 'Mission',
  components: {},
  data() {
    return {
      mission: [
        {
          name: 'Design Principles',
          list: [
            'Agile Development',
            'Open Source Software',
            'Collaboration / Cooperation',
            'Maximizing Functionality / Cost',
            'Using technology to serve the community at large'
          ]
        },
        {
          name: 'Fields of Focus / Interest',
          list: [
            'Public Research',
            'Environment',
            'Education',
            'Health',
            'Non-Profit / Social Enterprise'
          ]
        }
      ]
    }
  }
}
</script>

<style>
li {
  text-align: left;
}
</style>
