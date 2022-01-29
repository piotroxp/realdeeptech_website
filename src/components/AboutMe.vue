<template>
<div>
  <div class="container text-center">
    <h1>
      About Me
    </h1>
    <hr />
    </div>
    <div class="container text-align">
      <About />
    </div>
  </div>
</template>

<script>
import About from '@/../posts/data/about.md'

export default {
  name: 'AboutMe',
  components: {
    About: About.vue.component
  },
  mounted: function () {
    this.changeTitle('About')
  }
}
</script>
