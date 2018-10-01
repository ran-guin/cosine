<template lang='pug'>
  div.container
    p &nbsp;
    h1 Skills & Expertise
    hr
    div.flex-container
      span.flex-item(v-for="skill in skills")
        h2 
          fa.icon(:icon='skill.icon')
          span &nbsp; &nbsp; {{skill.name}}
        br
        div.block(v-if='skill.description') {{skill.description}}
        div.listBlock
          ul
          span(v-for="item in skill.list")
            li {{item}}
      div.wide-item &nbsp;
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
.flex-container {
  display: flex;
  flex-direction: row col;
  flex-wrap: wrap;
}
.flex-item {
  border: 1px solid lightgrey;
  padding: 2rem;
  width: 50%;
}
.wide-item {
  width: 100%;
  padding: 2rem;
}
.boxed {
  border: solid black 1px;
  padding: 2rem;
}
.block {
  // border: solid black 1px;
  padding: 0rem;
  padding-left: 2rem;
}
.listBlock {
  padding: 0rem;
  padding-left: 4rem;
}
.toolbox {
  background-color: lightgrey;
}
.toolsLogo {
  max-height: 100px;
  padding: 20px;
}
.icon {
  text-align: center;
}
</style>
