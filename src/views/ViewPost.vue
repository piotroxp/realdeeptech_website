<template>
  <div>
  <div class="cover-div">
  <center>
    <img :src="post.cover" class="cover" />
    </center>
    </div>
    <div class="container">
      <div class="text-center">
        <h1 class="headline">{{ post.title }}</h1>
        <p>
          Posted on: {{ `${post.date[0]}/${post.date[1]}/${post.date[2]}` }}
        </p>
        <div class="center">
          <Avatar :postauthor="post.author"/>
          <span class="margin">
            {{ config.username }}
          </span>
        </div>
      </div>
      <hr>
      <router-view class="post"></router-view>
      <PostTags :postTags="post.tags" />
      <PostNavBtn :prev="prevPost" :next="nextPost" />
    </div>
  </div>
</template>

<script>
import Posts from '@/../posts/data/posts.json'
import Avatar from '@/components/Avatar.vue'
import Config from '@/../posts/data/config.json'
import PostNavBtn from '@/components/PostNavBtn.vue'
import PostTags from '@/components/PostTags.vue'

export default {
  name: 'ViewPost',
  components: {
    Avatar,
    PostNavBtn,
    PostTags
  },
  data: function () {
    return {
      postId: this.$route.path.split('posts/')[1],
      posts: Posts.posts,
      post: {
        title: null,
        date: [
          null,
          null,
          null
        ],
        tags: [],
        author: null
      },
      config: Config.config,
      prevPost: {
        title: null,
        id: null
      },
      nextPost: {
        title: null,
        id: null
      }
    }
  },
  methods: {
    getPost: function () {
      // because of markdown file rendering, can't use the triditional dynamic route matching
      this.postId = this.$route.path.split('posts/')[1]
      const curPostIdx = this.posts.findIndex((post) => post.id === this.postId)
      if (curPostIdx >= 0) { // post found
        this.post = this.posts[curPostIdx]
        this.changeTitle(this.post.title)
        try {
          if (curPostIdx > 0) { // has a previous post (not the first one)
            this.nextPost.title = this.posts[curPostIdx - 1].title
            this.nextPost.id = this.posts[curPostIdx - 1].id
          } else {
            this.nextPost.id = null
          }
          if (curPostIdx < this.posts.length - 1) { // has a next post (not the last one)
            this.prevPost.title = this.posts[curPostIdx + 1].title
            this.prevPost.id = this.posts[curPostIdx + 1].id
          } else {
            this.prevPost.id = null
          }
        } catch (err) {
          console.log(err) // Handle error
        }
      }
    }
  },
  mounted: function () {
    this.getPost()
  },
  watch: {
    $route (to, from) {
      this.getPost()
    }
  }
}
</script>

<style>
.cover-div{
  width: 100vw;
  background-color: gray;  
  padding:10px;
  padding-top:18px;
}


.post img {  /* limit image max width to 100vw in a post */
    max-width: 100vw;
} 

/* Portrait and Landscape */
@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 480px)
  and (-webkit-min-device-pixel-ratio: 2) {
    .cover {
      padding:0;
      width: 100vw;
    }
}

/* Portrait */
@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 480px)
  and (-webkit-min-device-pixel-ratio: 2)
  and (orientation: portrait) {
    .cover {
      padding:0;
      width: 100vw;
    }
}

/* Landscape */
@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 480px)
  and (-webkit-min-device-pixel-ratio: 2)
  and (orientation: landscape) {
    .cover {
      padding:0;
      width: 100vw;
    }
}

/* ----------- iPhone 5, 5S, 5C and 5SE ----------- */

/* Portrait and Landscape */
@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 568px)
  and (-webkit-min-device-pixel-ratio: 2) {
    .cover {
      padding:0;
      width: 100vw;
    }
}

/* Portrait */
@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 568px)
  and (-webkit-min-device-pixel-ratio: 2)
  and (orientation: portrait) {
    .cover {
      padding:0;
      width: 100vw;
    }
}

/* Landscape */
@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 568px)
  and (-webkit-min-device-pixel-ratio: 2)
  and (orientation: landscape) {
    .cover {
      padding:0;
      width: 100vw;
    }
}

/* ----------- iPhone 6, 6S, 7 and 8 ----------- */

/* Portrait and Landscape */
@media only screen 
  and (min-device-width: 375px) 
  and (max-device-width: 667px) 
  and (-webkit-min-device-pixel-ratio: 2) { 
    .cover {
      padding:0;
      width: 100vw;
    }
}

/* Portrait */
@media only screen 
  and (min-device-width: 375px) 
  and (max-device-width: 667px) 
  and (-webkit-min-device-pixel-ratio: 2)
  and (orientation: portrait) { 
    .cover {
      padding:0;
      width: 100vw;
    }
}

/* Landscape */
@media only screen 
  and (min-device-width: 375px) 
  and (max-device-width: 667px) 
  and (-webkit-min-device-pixel-ratio: 2)
  and (orientation: landscape) { 
    .cover {
      padding:0;
      width: 100vw;
    }
}

/* ----------- iPhone 6+, 7+ and 8+ ----------- */

/* Portrait and Landscape */
@media only screen 
  and (min-device-width: 414px) 
  and (max-device-width: 736px) 
  and (-webkit-min-device-pixel-ratio: 3) { 
    .cover {
      padding:0;
      width: 100vw;
    }
}

/* Portrait */
@media only screen 
  and (min-device-width: 414px) 
  and (max-device-width: 736px) 
  and (-webkit-min-device-pixel-ratio: 3)
  and (orientation: portrait) { 
    .cover {
      padding:0;
      width: 100vw;
    }
}

/* Landscape */
@media only screen 
  and (min-device-width: 414px) 
  and (max-device-width: 736px) 
  and (-webkit-min-device-pixel-ratio: 3)
  and (orientation: landscape) { 
    .cover {
      padding:0;
      width: 100vw;
    }
}

/* ----------- iPhone X ----------- */

/* Portrait and Landscape */
@media only screen 
  and (min-device-width: 375px) 
  and (max-device-width: 812px) 
  and (-webkit-min-device-pixel-ratio: 3) { 
    .cover {
      padding:0;
      width: 100vw;
    }
}

/* Portrait */
@media only screen 
  and (min-device-width: 375px) 
  and (max-device-width: 812px) 
  and (-webkit-min-device-pixel-ratio: 3)
  and (orientation: portrait) { 
    .cover {
      padding:0; 
      width: 100vw;
    }
}

/* Landscape */
@media only screen 
  and (min-device-width: 375px) 
  and (max-device-width: 812px) 
  and (-webkit-min-device-pixel-ratio: 3)
  and (orientation: landscape) { 
    .cover {
      padding:0;
      width: 100vw;
    }
}

.margin {
  margin-left: 20px;
}

</style>
