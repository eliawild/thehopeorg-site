<template>
  <Layout>
    <h1>{{ $page.redditPost.title }}</h1>
  </Layout>
</template>

<page-query>
query RedditPost ($path: String!) {
  redditPost: redditPost (path: $path) {
    title
    path
  }
}
</page-query>

<script>
export default {
  metaInfo () {
    return {
      title: this.$page.redditPost.title
    }
  }
}
</script>
