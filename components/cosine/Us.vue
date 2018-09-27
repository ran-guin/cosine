<template lang='pug'>
	div
		hr
		span.container.col-md-3(v-for="skill in skills")
			// icon(:name="skill.icon")
			span &nbsp; {{skill.name}}
			p &nbsp;
			span {{skill.description}}
			ul
			span(v-for="item in skill.list")
				li {{item}}
		p &nbsp;
		hr
		span(v-for="image in tools")
			img.toolsLogo(:src='image')

</template>


<script>
// import 'vue-awesome/icons/eye'
// import 'vue-awesome/icons/signal'
// import 'vue-awesome/icons/globe'
// import 'vue-awesome/icons/desktop'

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
        '/static/images/lamp.jpg',
        '/static/images/bootstrap.png',
        '/static/images/node.png',
        '/static/images/angular.png',
        '/static/images/react.png',
        '/static/images/vue.png',
        '/static/images/adonis.jpg',
        '/static/images/d3t.jpg'
      ]
    }
  }
}
</script>

<style>
.boxed {
  border: solid black 1px;
}
.toolsLogo {
  max-height: 100px;
  padding: 20px;
}
</style>
