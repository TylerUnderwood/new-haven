<template>
  <Layout class="layout-resources">

    <intro
      top-title="Contractor"
      bottom-title="Resources">
      <p slot="copy">
        Newhaven Builders keeps excellent working relationships with its subs. If you or the company you represent is interested, we’d like to invite you to bid on future projects. Upon approval, you will be added to our subcontractor’s list and receive invitations to bid. Any questions, please don't hesitate to reach out.
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
    title: 'Contractor Resources'
  },
  
  components: {
    Intro,
  },

  data() {
    return {
      docLinks: [
        {
          name: 'Subcontractor Qualification Form' ,
          file: 'https://na3.docusign.net/Member/PowerFormSigning.aspx?PowerFormId=ea37c071-0e73-4624-a4f6-93f1adf19406&env=na3&acct=2dc8882f-5248-4ce6-b38c-9f31ade7d0ad&v=2',
          icon: 'pdf',
        },
        {
          name: 'Liability Cert Request' ,
          file: '/resources/newhaven-builders-liability-cert-request.pdf',
          icon: 'pdf',
        },
        {
          name: 'W9 Form' ,
          file: 'https://www.irs.gov/pub/irs-pdf/fw9.pdf',
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