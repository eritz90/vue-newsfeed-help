<template>
  <div class="newsfeed">
    <h1>This is the newsFeed page</h1>
    <form>
        <label>Post Title: </label>
        <input type="title" required v-model="title">
    </form>
    <form>
        <label>Body: </label>
        <input type="body" required class="body" v-model="body">
    </form>
    <button>Add Post</button>
    <p>Title: {{ title }} </p>
    <p>Body: {{ body }}</p>
    <PostList :posts="posts" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import PostList from '../components/PostList.vue';
// import Post from '../interface/Post';

export default defineComponent({
  name: 'Newsfeed',
  // components: { PostList },
  data() {
    return {
      title: '',
      body: '',
    };
  },
});
</script>>

<style>
    form{
        max-width: 420px;
        margin:30px auto;
        background: white;
        text-align: left;
        padding:40px;
        border-radius: 10px;
    }
    label {
        color: #aaa;
        display: inline-block;
        margin: 25px 0 15px;
        font-size: 0.6em;
        text-transform: uppercase;
        letter-spacing: 1px;
        font-weight: bold;
    }
    input {
        display: block;
        padding: 10px 6px;
        width: 100%;
        box-sizing: border-box;
        border: none;
        border-bottom: 1px solid #ddd;
        color: #555;
    }
    input.body{
        display: block;
        padding: 100px 6px;
        width: 100%;
        box-sizing: border-box;
        border: none;
        border-bottom: 1px solid #ddd;
        color: #555;
    }
</style>
