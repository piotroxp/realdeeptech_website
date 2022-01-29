<template>
  <div class="footer">
    <div class="container text-center">
      <h3>{{ page.blogTitle }}</h3>
      <p><i>{{ page.description }}</i></p>
      <p v-if="curYear === page.blogStartYear">
        &copy; {{ curYear }} {{ page.name }}
      </p>
      <p v-else>
        &copy; {{ page.blogStartYear }} - {{ curYear }} {{ page.name }}.&nbsp;
        Powered by <a href="https://github.com/samzhangjy/VueBlogger" target="_blank">VueBlogger</a>.
      </p>
    </div>
  </div>
</template>

<script>
import Config from '@/../posts/data/config.json'

export default {
  name: 'Footer',
  data: function () {
    return {
      page: Config.page,
      curYear: new Date().getFullYear()
    }
  },
  methods: {
    getYear: function () {
      return new Date().getFullYear()
    }
  }
}
</script>
