<template>
  <router-link :to="`/posts/${post.id}`">
    <vs-card class="post-card">
      <template #title>
        <h3>{{ post.title }}</h3>
        <small>{{ post.date[0] }}/{{ post.date[1] }}/{{ post.date[2] }}</small>
      </template>
      <template #img>
        <img :src="post.cover" class="no-bottom-border" alt />
      </template>
      <template #text>
        <p class="post-txt">{{ post.des }}</p>
        <small class="post-card-tag">
          <b :key="i" v-for="(tag, i) in post.tags" style="margin-right: 5px">
            {{ tag }}
          </b>
        </small>
      </template>
      <template #interactions>
        <vs-tooltip right shadow interactivity>
          <Avatar :postauthor="post.author" />
          <template #tooltip>
            Posted by
            <b>{{ config.username }}</b>
          </template>
        </vs-tooltip>
      </template>
    </vs-card>
  </router-link>
</template>

<script>
import Config from '@/../posts/data/config.json'
import Avatar from '@/components/Avatar.vue'

export default {
  name: 'PostCard',
  props: [
    'post'
  ],
  data: function () {
    return {
      config: Config.config
    }
  },
  components: {
    Avatar
  }
}
</script>

<style>
.post-txt {
  overflow: hidden;
  text-overflow: ellipsis;
  display: auto;
}

.post-card .vs-card {
  height: 380px !important;
  background-color: lightsteelblue;
}

[vs-theme=dark] .post-card .vs-card {
  height: 380px !important;
  background-color: steelblue;
}


.post-card-tag {
  position: absolute;
  bottom: 20px;
}

.no-bottom-border {
  border-radius:0px !important;
}
</style>
