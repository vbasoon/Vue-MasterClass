<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br />
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener"
        >vue-cli documentation</a
      >.
    </p>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li>
        <a
          href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel"
          target="_blank"
          rel="noopener"
          >babel</a
        >
      </li>
      <li>
        <a
          href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint"
          target="_blank"
          rel="noopener"
          >eslint</a
        >
      </li>
    </ul>
    <h3>Essential Links</h3>
    <ul>
      <li>
        <a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a>
      </li>
      <li>
        <a href="https://forum.vuejs.org" target="_blank" rel="noopener"
          >Forum</a
        >
      </li>
      <li>
        <a href="https://chat.vuejs.org" target="_blank" rel="noopener"
          >Community Chat</a
        >
      </li>
      <li>
        <a href="https://twitter.com/vuejs" target="_blank" rel="noopener"
          >Twitter</a
        >
      </li>
      <li>
        <a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a>
      </li>
    </ul>
    <h3>Ecosystem</h3>
    <ul>
      <li>
        <a href="https://router.vuejs.org" target="_blank" rel="noopener"
          >vue-router</a
        >
      </li>
      <li>
        <a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a>
      </li>
      <li>
        <a
          href="https://github.com/vuejs/vue-devtools#vue-devtools"
          target="_blank"
          rel="noopener"
          >vue-devtools</a
        >
      </li>
      <li>
        <a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener"
          >vue-loader</a
        >
      </li>
      <li>
        <a
          href="https://github.com/vuejs/awesome-vue"
          target="_blank"
          rel="noopener"
          >awesome-vue</a
        >
      </li>
    </ul>
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
