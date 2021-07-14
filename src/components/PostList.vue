<template>
  <div class="post-list">
    <!-- <posts :posts="posts"/> -->
    <ul>
      <li v-for="post in posts" :key="post.id">
        <h2>{{ posts.title }}</h2>
        <div class="id">
          <p>{{ post.id }} : author </p>
        </div>
        <div class="description">
          <p>{{ post.body }}</p>
          <button>Edit Post</button>
          <button>Delete Post</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import Post from '../interface/Post';
import { postsList } from '../composables/use-post';

export default defineComponent({
  name: 'PostList',
  components: { postsList },
  props: {
    posts: {
      type: Array as PropType<Post[]>,
      required: true,
    },
  },
});
</script>

<style scoped>
  .post-list {
    max-width: 960px;
    margin: 40px auto;
  }
  .post-list ul {
    padding: 0;
  }
  .post-list li {
    list-style-type: none;
    background: white;
    padding: 16px;
    margin: 16px 0;
    border-radius: 4px;
  }
  .post-list h2 {
    margin: 0 0 10px;
    text-transform: capitalize;
  }
  .id {
    display: flex;
  }
  .id img {
    width: 30px;
  }
  .id p {
    color: #17bf66;
    font-weight: bold;
    margin: 10px 4px;
  }
</style>
