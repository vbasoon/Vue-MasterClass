<template>
  <div class="hello">
    <div style="font-weight: 900">
      Contributors:
      <div v-for="u in users" :key="u.id">
        {{ u.name }}
      </div>
    </div>
    <hr />
    <div>
      Categories:
      <div v-for="c in categories" :key="c.id">{{ c.name }}</div>
    </div>
    <hr />
    <div style="font-weight: 900">
      Forums:
      <div v-for="f in forums" :key="f.id">
        <span style="font-weight: 900; text-decoration: none">{{
          f.name
        }}</span>
      </div>
    </div>
    <hr />
    <div>
      <h2>Threads:</h2>
      <hr />
      <div v-for="t in threads" :key="t.id">
        <div>
          <span style="color: red; font-weight: bold">Theme:</span>
          {{ t.title }}
        </div>
        <div>
          <span style="color: red; font-weight: bold">Published At:</span>
          {{ t.publishedAt }}
        </div>
        <div>
          <span style="color: red; font-weight: bold">Contributors:</span>
          {{ t.contributors }}
        </div>
        <div>
          <span style="color: red; font-weight: bold">Last post:</span>
          {{ t.lastPostId }}
        </div>
        <div>
          <span style="color: red; font-weight: bold">Posts:</span>
          {{ t.posts }}
        </div>

        <hr />
      </div>
      <div>
        <h3>Statistics:</h3>

        <p><span>Posts Count: </span>{{ stats.postsCount }}</p>
        <p><span>Threads Count: </span>{{ stats.threadsCount }}</p>
        <p><span>Users Count: </span>{{ stats.usersCount }}</p>
        <p><span>User Online: </span>{{ stats.usersOnline }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import sourceData from "@/data.json";
console.log(sourceData);
console.log(sourceData.categories);
console.log(sourceData.threads);
console.log(sourceData.posts);
console.log(sourceData.forums);
console.log(sourceData.stats);
console.log(sourceData.users);
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      categories: sourceData.categories,
      threads: sourceData.threads,
      forums: sourceData.forums,
      posts: sourceData.posts,
      users: sourceData.users,
      stats: sourceData.stats,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
