<script>
export default {
  name: 'ArticleWithMedia',
  props: {
    main: { type: Boolean, required: false },
    title: { type: String, required: true },
    text: { type: String, required: true },
    link: { type: Object, required: false },
    left: { type: Boolean, required: false }
  }
}
</script>

<template>
  <div class="article__media" :class="{ 'article__media--left': left }">
    <slot></slot>
  </div>
  <div class="row">
    <div
      class="col-24"
      :class="({ 'col-md-20 offset-md-4': $props.left,'col-md-22 offset-md-2': !$props.left })"
    >
      <article>
        <h1 v-if="$props.main" class="article__title">{{ $props.title }}</h1>
        <h2 v-else class="article__title">{{ $props.title }}</h2>
        <p>
          {{ $props.text }}
        </p>
        <a v-if="$props.link" class="article__link" :href="$props.link.url"
          >{{ $props.link.urlText }} <i class="fa-solid fa-chevron-right"></i
        ></a>
      </article>
    </div>
  </div>
</template>

<style>
.article__title {
  margin-bottom: 0.8em;
}
h2.article__title {
  font-size: 1.7rem;
}
.article__link {
  display: inline-block;
  color: black;
  text-decoration: none;
  text-transform: uppercase;
  font-size: 12px;
  letter-spacing: 2px;
  margin-bottom: 4rem;
}

.article__media--left {
  margin-bottom: 4rem;
  position: relative;
}

@media (max-width: 768px) {
  .article__media--left {
    margin-bottom: 4rem;
  }
}
</style>
