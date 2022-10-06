<template>
  <div>Home Page</div>
  <div v-for="thread in threads" :key="thread.id">
    <h2>Threads:{{ thread.title }}</h2>
    <div v-for="postId in thread.posts" :key="postId">
      <p>
        {{
          users.find((u) => u.id === posts.find((p) => p.id === postId).userId)
            .name
        }}
      </p>
      <p>{{ posts.find((p) => p.id === postId).text }}</p>
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
    postById() {
      return null;
    },
    userById() {
      return null;
    },
  },
};
</script>

<style></style>
