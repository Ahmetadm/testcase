<script>
import EarthIcon from '@/components/icons/EarthIcon.vue'
import FooterCard from '@/components/Footer/FooterCard.vue'

export default {
  name: 'PageFooter',
  components: { FooterCard },
  data() {
    return {
      footerCardList: [
        { id: 1, title: 'Worldwide shipping', icon: EarthIcon },
        {
          id: 2,
          title: 'Customer service',
          icon: EarthIcon,
          link: {
            text: 'test@test.com',
            link: 'mailto:text@text.com'
          }
        },
        {
          id: 3,
          title: 'Phone number',
          icon: EarthIcon,
          link: {
            text: '+32 (0) 56 77 25 71',
            link: 'tel:+32056772571'
          }
        }
      ]
    }
  }
}
</script>

<template>
  <footer>
    <div class="container-fluid">
      <div class="row">
        <div v-for="card in footerCardList" class="col-24 col-md-8" :key="card.id">
          <FooterCard :title="card.title" :link="card.link" :icon="card.icon"> </FooterCard>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
footer {
  background-color: #899796;
  text-align: center;
  color: white;
  padding: 2rem 0;
}
@media (max-width: 768px) {
  .col-24.col-md-8:not(:last-child) {
    margin-bottom: 4rem;
  }
}
</style>
