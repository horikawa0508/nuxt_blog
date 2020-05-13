<template>
  <div>
    <TheHeader />
    <Index />
    <nuxt />
    <Footer/>
  </div>
</template>

<script>
import TheHeader from '@/components/common/Header.vue'
import Index from '@/components/common/Index.vue'
import Footer from '@/components/common/Footer.vue'


export default {
    components: {
    TheHeader,
    Index,
    Footer
  }
}
</script>
<style>

</style>
