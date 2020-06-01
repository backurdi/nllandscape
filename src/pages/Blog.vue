<template>
  <Layout>
    <h1 class="my-4 mb-5">Blog</h1>

    <div class="blog-content-container">
      <div class="blog-content" v-for="item in $page.posts.edges" :key="item.node.id">
        <g-link :to="item.node.path" class="blog-post">
          <div class="media m-1">
            <g-image immediate :src="item.node.image" class="mr-3" alt="image" />
            <div class="media-body">
              <h5 class="mt-0">{{item.node.title}}</h5>
              <p class="text-dark">{{item.node.excerpt}}</p>
            </div>
          </div>
        </g-link>
      </div>
    </div>
  </Layout>
</template>

<page-query>
query Blog {
	posts: allBlogPost(sortBy: "date") {
    edges {
      node {
        id
        path
        title
        excerpt
        image
      }
    }
  }
}
</page-query>

<style lang="scss" scoped>
.blog-content-container {
  display: flex;
  flex-wrap: wrap;

  .blog-content {
    width: 33%;
    flex-grow: 1;

    .media {
      border-radius: 5px;
      box-shadow: 4px 6px 48px -2px rgba(114, 136, 148, 1);
      display: flex;
      flex-direction: column;
      height: 250px;
      overflow: hidden;
      margin: 0;
      padding: 10px;

      img {
        width: 120px;
        height: 120px;
      }
    }

    .media-body {
      margin: auto;
    }
  }
}
</style>
