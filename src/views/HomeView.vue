<script setup>

import PageFooter from "@/components/Footer/Footer.vue";
import PageArticles from "@/components/Article/Articles.vue";
</script>

<template>
    <main>
        <div class="backgroundBox"></div>
        <section>
            <div class="container">
                <div class="row">
                  <PageArticles/>
                </div>
            </div>
        </section>
    </main>
  <PageFooter/>
</template>
<style>
main{
    padding: 7rem 0;
}
</style>