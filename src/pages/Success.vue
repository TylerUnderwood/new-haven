<template>
  <Layout class="layout-contact">

    <section class="frame gutter">
      <div class="inner">

			  <page-title topTitle="Success" />

      </div>
      <div class="outer md:gutter frame mb-0">
        <div class="inner flex">
          <div class="xl:w-1/2 flex justify-end pr-8 hide sm:show" appear="fade-up" appear-group="intro">
            <div class="accent-fork accent-fork--down">
              <div class="accent-fork__base"></div>
            </div>
          </div>
          <div class="xl:w-1/2" appear="fade-up" appear-group="intro">
            <p>Newhaven Builders is a company that prides itself on achieving client objectives.</p>
            <div class="accent-fork accent-fork--left mt-8 sm:hide">
              <div class="accent-fork__base"></div>
            </div>
          </div>
        </div>
      </div>
    </section>

  </Layout>
</template>

<script>
import PageTitle from '../components/PageTitle.vue';

export default {
  metaInfo: {
    title: 'Success'
  },

	components: {
		PageTitle,
	},
}
</script>