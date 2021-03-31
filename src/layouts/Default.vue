<template>
  <div id="template" class="template">

    <Header />
      
    <main id="main" class="main">

      <slot/>

    </main>

    <div class="trim"></div>

    <Footer />

    <site-guidelines/>
    
  </div>
</template>


<script>
import AppearAnimation from '~/js/appear-animation.js'
import Header from '~/components/Header.vue'
import Footer from '~/components/Footer.vue'
import SiteGuidelines from '../components/SiteGuidelines.vue'

export default {
  components: {
    Header,
    Footer,
    SiteGuidelines,
  },
      
  mounted() {
    setTimeout(() => {
      new AppearAnimation().init();
    }, 300);
  },
}
</script>