<script>
export default {
  name: 'FooterCard',

  props: {
    title: { type: String, required: true },
    link: { type: Object, required: false },
    icon: { type: Object, required: true }
  }
}
</script>

<template>
  <div class="footerCard">
    <component class="footerCard__icon" :is="icon">icon</component>
    <h4 class="footerCard__title">{{ $props.title }}</h4>
    <a v-if="$props.link" :href="`${$props.link.url}`" class="footerCard__text footerCard__link">
      {{ $props.link.text }}
    </a>
  </div>
</template>

<style>
.footerCard__text {
  margin-bottom: 0;
  font-size: 0.8rem;
  color: white;
}
.footerCard__icon {
  width: 60px;
  margin-bottom: 1.5rem;
}
.footerCard__link {
  text-transform: uppercase;
}
</style>