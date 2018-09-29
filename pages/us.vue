<template lang='pug'>
  div.container
    p &nbsp;
    h2 Skills & Expertise
    hr
    span.container.col-md-6(v-for="skill in skills")
      h4 
        fa.icon(:icon='skill.icon')
        span &nbsp; &nbsp; {{skill.name}}
      br
      span.block
        p {{skill.description}}
        ul
        span(v-for="item in skill.list")
          li {{item}}
      hr

    p &nbsp;
    span(v-for="image in tools")
      img.toolsLogo(:src='image')

</template>

<script>
export default {
  name: 'Us',
  components: {},
  data() {
    return {
      skills: [
        {
          icon: 'desktop',
          name: 'Web Sites',
          description:
            'We can develop customized single-page or multi-page web sites that effectively communicate who you are and what you have to offer'
        },
        {
          icon: 'globe',
          name: 'Web Applications',
          description:
            'We can also develop more comprehensive web applications with personalized user login features, a database backend, and customized data handling and visualization'
        },
        {
          icon: 'signal',
          name: 'Data Management',
          list: [
            'Database Design',
            'Data Standardization',
            'Streamlining Data Entry',
            'Data Mining',
            'Data Storage',
            'REST API development'
          ]
        },
        {
          icon: 'eye',
          name: 'Data Visualization',
          description: 'Generating simple ways to visualize data effectively',
          list: [
            'Dynamic Graphs / Bar Charts',
            'Annotated Data Maps',
            'Excel/PDF Reports'
          ]
        }
      ],

      tools: [
        '/images/cosine/lamp.jpg',
        '/images/cosine/bootstrap.png',
        '/images/cosine/node.png',
        '/images/cosine/angular.png',
        '/images/cosine/react.png',
        '/images/cosine/vue.png',
        '/images/cosine/adonis.jpg',
        '/images/cosine/d3t.jpg'
      ]
    }
  }
}
</script>
<style>
.boxed {
  border: solid black 1px;
  padding: 2rem;
}
.block {
  // border: solid black 1px;
  padding: 2rem;
}
.toolsLogo {
  max-height: 100px;
  padding: 20px;
}
.icon {
  text-align: center;
}
</style>
