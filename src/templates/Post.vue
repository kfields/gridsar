<template>
  <Layout>
    <article>
      <g-image class="heroImage" :alt="$page.post.title" :src="$page.post.cover"/>
      <div class="section">
        <div>
          <h1>{{$page.post.title}}</h1>
          <p style="display: block">{{$page.post.date}}</p>
        </div>
        <div v-html="markdown"/>
      </div>
    </article>
  </Layout>
</template>

<page-query>
  query BlogPost ($path: String!) {
    post (path: $path) {
      title
      date (format: "D MMMM, YYYY")
      content
      cover
    }
  }
</page-query>

<script>
import marked from "marked";
export default {
  name: "Contentful",
  // props: [''],
  // components: {},
  data() {
    return {
      markdown: ""
    };
  },
  metaInfo() {
    return {
      title: this.$page.post.title,
      meta: [{ name: "description", content: this.$page.post.description }]
    };
  },
  mounted: function() {
    this.markdown = marked(this.$page.post.content);
  }
};
</script>
<style>
article ul {
  list-style: disc inside;
  margin-bottom: 1rem;
}
article ul li {
  margin-bottom: 1rem;
}

</style>