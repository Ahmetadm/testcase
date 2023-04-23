<script>
import ArticleVideo from '@/components/ArticleVideo.vue'
import articleVideo from '@/assets/video/textiles_of_the_future.mp4'

export default {
    name: 'PageArticles',
    components: { ArticleVideo },
    setup() {
        return {
            articleVideo
        }
    },
}
</script>
<template>
  <div class="col-24 col-md-12 article">
    <div class="article__image article__image--left">
      <ArticleVideo :src="articleVideo" />
    </div>
    <div class="row">
      <div class="col-24 col-md-20 offset-md-4">
        <article>
          <h2 class="article__title">Our Story</h2>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium tempore quam
            molestias aliquid quaerat impedit, non saepe eum sequi consequatur itaque dolorem
            suscipit quis eligendi at quisquam? Omnis facilis vero accusamus voluptatem
          </p>
          <a class="article__link" href="#">Read more <i class="fa-solid fa-chevron-right"></i></a>
        </article>
      </div>
    </div>
  </div>
  <div class="col-24 offset-md-1 col-md-11 article article--reverse">
    <div class="article__image article__image--right">
      <img src="../assets/img/textile.jpeg" alt="" />
    </div>
    <div class="row">
      <div class="col-24 col-md-22 offset-md-2">
        <article>
          <h1 class="article__title">We speak textile</h1>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium tempore quam
            molestias aliquid quaerat impedit, non
          </p>
          <a class="article__link" href="#">Read more <i class="fa-solid fa-chevron-right"></i></a>
        </article>
      </div>
    </div>
  </div>
</template>



<style scoped></style>
