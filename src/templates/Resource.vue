<template>
  <Layout class="layout-resource">

    <intro
      :top-title="$page.resource.titlePart1"
      :bottom-title="$page.resource.titlePart2">
      <p slot="copy">
        {{ $page.resource.intro }}
      </p>
    </intro>

    <section class="frame gutter">
      <div class="inner">

        <g-link 
          class="download-link mxw-640" 
          v-for="(resourceLink, index) in $page.resource.resourceLinks" 
          :key="`download-link-${index}`" 
          :to="`/resources/${resourceLink.file}`" 
          target="_blank">
          <span class="icon mr-6">
            <g-image v-if="resourceLink.icon === 'pdf'" src="~/assets/svg/icon-pdf.svg" />
            <g-image v-if="resourceLink.icon === 'doc'" src="~/assets/svg/icon-doc.svg" />
          </span>
          <span class="text meta">
            {{ resourceLink.name }}
          </span>
        </g-link>

      </div>
    </section>

  </Layout>
</template>


<script>
import Intro from '~/components/Intro.vue'

export default {
  name: "Resource",

  components: {
    Intro,
  },
}
</script>


<page-query>
query Resource($path: String) {
  resource(path: $path) {
    id
    slug
    path
    title
    titlePart1
    titlePart2
    intro
    resourceLinks {
      name
      file
      icon
    }
  }
}
</page-query>