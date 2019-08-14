<template>
  <Layout>

    <p>
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur excepturi labore tempore expedita, et iste tenetur suscipit explicabo! Dolores, aperiam non officia eos quod asperiores
    </p>

    <h2>Automatic Blogroll</h2>

    <ul>
      <li v-for="post in $page.posts.edges" :key="post.id">
        <g-link :to="post.node.path">
          {{ post.node.title }}
        </g-link>
      </li>
    </ul>

    <!-- <h2>Reddit /r/aww</h2> -->

    <!-- <ul class="post">
      <li v-for="post in $page.redditPosts.edges" :key="post.id">
        <img :src="post.node.thumbnail" alt="img">
        <g-link :to="post.node.path">{{ post.node.title }}</g-link>
      </li>
    </ul> -->

    <!-- <p class="home-links">
      <a href="https://gridsome.org/docs" target="_blank" rel="noopener">Gridsome Docs</a>
      <a href="https://github.com/gridsome/gridsome" target="_blank" rel="noopener">GitHub</a>
    </p> -->

  </Layout>
</template>

<page-query>
query {
  posts: allPost {
    edges {
      node {
        id
        title
        path
      }
    }
  }
  redditPosts: allRedditPost {
    edges {
      node {
        id
        title
        path
        thumbnail
      }
    }
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: 'Home'
  }
}
</script>

<style>

.home-links a {
  margin-right: 1rem;
}

</style>
