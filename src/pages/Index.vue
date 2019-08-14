<template>
  <Layout>

    <h2 class="text-4xl">Regenesis</h2>

    <ul class="text-blue-600">
      <li v-for="post in $page.posts.edges" :key="post.id">
        <g-link :to="post.node.path">
          {{ post.node.title }}
        </g-link>
      </li>
    </ul>

    <!-- <h2 class="text-4xl pt-5">Reddit /r/kabbalah</h2>

    <ul class="post text-blue-600">
      <li v-for="post in $page.redditPosts.edges" :key="post.id">
        <g-link :to="post.node.path">{{ post.node.title }}</g-link>
      </li>
    </ul> -->

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
