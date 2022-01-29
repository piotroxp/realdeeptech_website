<template>
  <div :class="`${home ? 'avatar-home' : ''}`">
    <vs-avatar :size="size" circle >
      <img
        :src="avatarPath"
      >
    </vs-avatar>
  </div>
</template>

<script>
import Config from '@/../posts/data/config.json'

export default {
  name: 'Avatar',
  data: function () {
    return {
      config: Config.config,
    }
  },
  computed: {
    avatarPath() {
      return 'authors/' + this.postauthor + '.jpg';
    }
  },
  props: [
    'postauthor',
    'size',
    'home'
  ]
}
</script>

<style scoped>
.avatar-home .vs-avatar, .avatar-home .vs-avatar-content {
  min-width: 200px !important;
  min-height: 200px !important;
}
</style>
