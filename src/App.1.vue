<template>
  <div id="app">
    <button @click="fetchPosts">불러오기</button>
    <ul>
      <li v-for="post in posts">
        <h1>{{ post.title }}</h1>
        <p>{{ post.body }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      posts: []
    }
  },
  methods: {
    fetchPosts () {
      this.axios.get('https://jsonplaceholder.typicode.com/posts', {
        params: {
          userId: 1
        }
      }).then((res) => {
        this.posts = res.data
      })
    }
  }
}
</script>

<style lang="scss">
$point-color : red;
  ul {
    li {
      h1 {
        font-size:20pt;
        color: black;
      }
      p {
        font-size:10pt;
        color:$point-color;
      }
      list-style-type: none;

    }
  }
</style>
