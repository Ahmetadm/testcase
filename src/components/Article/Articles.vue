<script>
import ArticleVideo from '@/components/ArticleVideo.vue'
import articleVideo from '@/assets/video/textiles_of_the_future.mp4'
import ArticleWithMedia from '@/components/Article/Article.vue'

export default {
  name: 'PageArticles',
  components: { ArticleWithMedia, ArticleVideo },
  setup() {
    return {
      articleVideo
    }
  }
}
</script>
<template>
  <div class="col-24 col-md-12 article">
    <ArticleWithMedia
      :left="true"
      title="Our Story"
      text="  Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium tempore quam
            molestias aliquid quaerat impedit, non amet consectetur adipisicing elit. Laudantium tempore quam
            molestias aliquid quaerat impedit, non"
      :link="{ url: '#', urlText: 'read more' }"
    >
      <ArticleVideo :src="articleVideo" />
    </ArticleWithMedia>
  </div>
  <div class="col-24 offset-md-1 col-md-11 article article--reverse">
    <ArticleWithMedia
      main
      title="We speak textile"
      text="Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium tempore quam
            molestias aliquid quaerat impedit, non"
      :link="{ url: '#', urlText: 'read more' }"
    >
      <img src="../../assets/img/textile.jpeg" alt=""
    /></ArticleWithMedia>
  </div>
</template>

<style>
.article {
  display: flex;
  flex-direction: column;
}
.article--reverse {
  flex-direction: column-reverse;
  justify-content: flex-end;
}
.article--reversed .article--title {
  margin-top: 3rem;
}
@media (max-width: 768px) {
  .article--reverse {
    flex-direction: column;
    justify-content: flex-end;
  }
  .article--reverse .article__title {
    margin-top: 4rem;
  }
}
</style>
