<template>
  <Layout>
    <img class="greet-image" src="../../uploads/hello.svg" />

    <h2 class="mb-4">Gridsome starter bootstrap</h2>

    <Carousel>
      <slide>
        <p>Hello</p>
      </slide>
      <slide>
        <p>World</p>
      </slide>
      <slide>
        <p>World</p>
      </slide>
      <slide>
        <p>World</p>
      </slide>
      <slide>
        <p>World</p>
      </slide>
    </Carousel>
  </Layout>
</template>

<script>
import { Carousel, Slide } from "vue-carousel";

export default {
  components: {
    Carousel,
    Slide,
  },

  metaInfo: {
    title: "Gridsome starter bootstrap",
  },
};
</script>

<style>
.greet-image {
  display: block;
  margin: auto;
  width: 90%;
  max-width: 500px;
  padding-bottom: 50px;
}
</style>
