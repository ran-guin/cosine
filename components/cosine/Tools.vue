<template lang='pug'>
	div.container
		h3 Tools
		hr
		div.col-md-4(v-for="image in images")
			img.toolsLogo(:src='image')
</template>

<script>
export default {
  name: 'Tools',
  components: {},
  data() {
    return {
      footerImages: [
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

<style lang="sass?outputStyle=expanded">

.toolsLogo {
	max-height: 50px;
	padding: 20px;
}
/*** Customize Header / Footer Settings: ***/
</style>
