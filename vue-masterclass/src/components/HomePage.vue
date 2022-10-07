<template>
  <div>Home Page</div>
  <div v-for="thread in threads" :key="thread.id" class="col-large push-top">
    <h2>Threads:{{ thread.title }}</h2>
    <div class="post-list">
      <div v-for="postId in thread.posts" :key="postId">
        <p>{{ userById(postById(postId).userId).name }}</p>
        <p>{{ postById(postId).text }}</p>
      </div>
      <div class="post" v-for="postId in thread.posts" :key="postId">
        <div class="user-info">
          <a href="#" class="user-name">{{
            userById(postById(postId).userId).name
          }}</a>
          <a href="#">
            <img class="avatar-large" src="" alt="" />
          </a>
          <div class="stats">
            <p class="stats__posts">count_posts</p>
            <p class="stats__threads">count_threads</p>
            <p class="stats__status">Online</p>
          </div>
        </div>
        <div class="post__content">
          <div>
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Debitis
              possimus ratione voluptates, dolorum minima quis illo perspiciatis
              quam cupiditate autem, corrupti, asperiores id ut magni recusandae
              ullam consequuntur nesciunt?
            </p>
          </div>
          <a href="#" title="Edit"></a>
        </div>
        <div class="post-date">6 hours ago</div>
        <div class="reaction">
          <ul>
            <li>Reaction1</li>
            <li>Reaction2</li>
            <li>Reaction3</li>
            <li>Reaction4</li>
            <li>Reaction5</li>
            <li>Reaction6</li>
          </ul>
          <button><span>1</span></button>
          <button><span>2</span></button>
          <button><span>3</span></button>
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
