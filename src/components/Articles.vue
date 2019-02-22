<template>
  <div class="section">
    <ul class="article-list">
      <li v-for="edge in $static.posts.edges" :key="edge.id">
        <ArticlePreview :article="edge.node" />
      </li>
    </ul>
  </div>
</template>
<static-query>
  query HomeQuery {
    posts: allPost {
      edges {
        node {
          title
          description
          slug
          date(format: "MMMM Do, YYYY")
          tags
          cover
          description
        }
      }
    }
  }
</static-query>
<script>

export default {
  components: {
  },
};
</script>
