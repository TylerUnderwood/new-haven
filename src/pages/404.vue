<template>
  <Layout class="layout-404">

    <section class="trim gutter">
      <div class="inner">

			  <page-title topTitle="404" bottomTitle="not found" />

        <div class="frame mb-0" appear="fade-left" appear-group="intro">
          <h3>{{ this.$route.params.pathMatch }}</h3>
        </div>

      </div>
    </section>

  </Layout>
</template>

<script>
import PageTitle from '../components/PageTitle.vue';

export default {
  metaInfo: {
    title: '404'
	},

	components: {
		PageTitle,
	},
	
  mounted() {
    // console.log(this.$route.params.pathMatch);
  }
}
</script>
