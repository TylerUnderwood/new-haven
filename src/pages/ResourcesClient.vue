<template>
  <Layout class="layout-resources">

    <intro
      top-title="Client"
      bottom-title="Resources">
      <p slot="copy">
        Below you’ll find a section of resources to help with your decision making process.  Please don’t hesitate to request additional information.
      </p>
    </intro>

    <section class="frame gutter">
      <div class="inner">

        <g-link 
          class="download-link mxw-640" 
          v-for="(docLink, index) in docLinks" 
          :key="`download-link-${index}`" 
          :to="`${docLink.file}`" 
          target="_blank">
          <span class="icon mr-6">
            <g-image v-if="docLink.icon === 'pdf'" src="~/assets/svg/icon-pdf.svg" />
            <g-image v-if="docLink.icon === 'doc'" src="~/assets/svg/icon-doc.svg" />
          </span>
          <span class="text meta">
            {{ docLink.name }}
          </span>
        </g-link>

      </div>
    </section>

  </Layout>
</template>

<script>
import Intro from '~/components/Intro.vue'

export default {
  metaInfo: {
    title: 'Client Resources'
  },
  
  components: {
    Intro,
  },

  data() {
    return {
      docLinks: [
        {
          name: 'Ken Rideout Resume' ,
          file: '/resources/ken_rideout_resume.pdf',
          icon: 'pdf',
        },
        {
          name: 'Client Package' ,
          file: '/resources/newhaven-builders-company-introduction.pdf',
          icon: 'pdf',
        },
        {
          name: 'Letters of Recommendation' ,
          file: '/resources/letters-of-recommendations.pdf',
          icon: 'pdf',
        },
      ],
    }
  },
}
</script>


<page-query>
query Home {
  resources: allResource(sortBy: "id", order: ASC) {
    edges {
      node {
        id
        path
        title
      }
    }
  }
}
</page-query>