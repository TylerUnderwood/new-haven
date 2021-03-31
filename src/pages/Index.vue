<template>
  <Layout class="layout-homepage">

    <section class="hero md:gutter" appear>
      <div class="hero__inner outer frame mt-0">
        <g-image class="hero__image" src="~/assets/hero-home.jpg" />
        <div class="hero__outline"></div>
        <g-image class="hero__curve" src="~/assets/svg/curve.svg" />
      </div>
      <div class="hero__accent">
        <g-image class="hero__deco" src="~/assets/svg/flower.svg" />
      </div>
    </section>

    <section class="frame gutter">
      <div class="wrapper flex flex-col items-center">

        <h1 class="page-title">
          <span class="page-title__top" appear="fade-right">
            Homes Built
          </span>
          <span class="page-title__bottom" appear="fade-left">
            Around You
          </span>
        </h1>

        <div class="flex justify-between items-center trim">
          <div class="accent-fork accent-fork--right accent-fork--homepage" appear="fade-left">
            <div class="accent-fork__base"></div>
          </div>
          <div class="caption large text-accent px-8 flex flex-col md:flex-row justify-between items-center">
            <span>Design&nbsp;+&nbsp;Build</span>
            <span class="big-pipline hide md:show"></span>
            <span class="mt-2 md:mt-0">Construction</span>
          </div>
          <div class="accent-fork accent-fork--left accent-fork--homepage" appear="fade-right">
            <div class="accent-fork__base"></div> 
          </div>
        </div>

        <div class="text-center">
          <p class="text-xl">We've been building and remodeling custom homes in and around the Los Angeles area for over 30 years. Our commitment to superb quality and relationships means you're in caring hands.</p>
        </div>

      </div>
    </section>

    <project-cards />

    <working-together-cta />

  </Layout>
</template>

<script>
import ProjectCards from '../components/ProjectCards.vue'
import WorkingTogetherCta from '~/components/WorkingTogetherCta.vue'

export default {
  metaInfo: {
    title: 'Homepage'
  },
  components: {
    ProjectCards,
    WorkingTogetherCta,
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