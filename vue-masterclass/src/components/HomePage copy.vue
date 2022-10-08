<template>
  <div v-for="thread in threads" :key="thread.id" class="col-large push-top">
    <h2>Threads:{{ thread.title }}</h2>
    <div class="post-list">
      <div class="post" v-for="postId in thread.posts" :key="postId">
        <div class="user-info">
          <a href="#" class="user-name">{{
            userById(postById(postId).userId).name
          }}</a>
          <a href="#">
            <img
              class="avatar-large"
              :src="userById(postById(postId).userId).avatar"
              alt="avatar"
            />
          </a>

          <p class="stats__posts">count_posts</p>
        </div>
        <div class="post__content">
          <div>
            <p>
              {{ postById(postId).text }}
            </p>
          </div>
        </div>
        <div class="post-date text-faded">
          {{ postById(postId).publishedAt }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import sourceData from "@/data.json";
export default {
  data() {
    return {
      threads: sourceData.threads,
      posts: sourceData.posts,
      users: sourceData.users,
    };
  },
  methods: {
    postById(postId) {
      return this.posts.find((p) => p.id === postId);
    },
    userById(userId) {
      return this.users.find((p) => p.id === userId);
    },
  },
};
</script>

<style></style>
