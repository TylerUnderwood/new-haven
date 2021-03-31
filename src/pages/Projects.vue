<template>
  <Layout class="layout-projects">

    <section class="frame trim gutter">
      <div class="wrapper">

			  <page-title topTitle="Projects" bottomTitle="Built By Us" />

      </div>
    </section>

    <project-cards />

  </Layout>
</template>

<script>
import PageTitle from '../components/PageTitle.vue';
import ProjectCards from '../components/ProjectCards.vue'

export default {
  metaInfo: {
    title: 'Projects'
  },

  components: {
		PageTitle,
    ProjectCards,
  },
}
</script>

<page-query>
  query Home {
    projects: allProject(sortBy: "id", order: ASC) {
      edges {
        node {
          id
          path
          title
          featImage
          featImageAspect
          featCaption
          excerpt
        }
      }
    }
  }
</page-query>