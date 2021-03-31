<template>
  <Layout class="layout-project">

    <intro
      :top-title="$page.project.titlePart1"
      :bottom-title="$page.project.titlePart2">
      <div class="flex flex-col w-320" slot="info">
        <template v-for="(contributor, index) in $page.project.contributors">
          <span 
            :key="`contributor-label-${index}`"
            class="meta tiny" 
            :class="index > 0 ? 'mt-6' : null" 
            appear="fade-left" 
            appear-group="contributors">
            {{ contributor.label }}
          </span>
          <span 
            :key="`contributor-name-${index}`" 
            class="caption small mt-2"
            appear="fade-left" 
            appear-group="contributors">
            <template 
              v-for="line in contributor.name.split('\n')">
              {{ line }}<br v-if="!!line"/>
            </template>
          </span>
        </template>
      </div>
      <p slot="copy">
        {{ $page.project.intro }}
      </p>
    </intro>

    <template v-for="(section, index) in $page.project.sections">
      <component :is="section.type" :key="`${$page.project.slug}-${index}`" :data="section"></component>
    </template>

    <projects-cta />

    <working-together-cta />

  </Layout>
</template>

<script>
import Intro from '~/components/Intro.vue'
import FullImage from '~/components/FullImage.vue'
import DoubleImage from '~/components/DoubleImage.vue'
import TripleImage from '~/components/TripleImage.vue'
import ImageLeft from '~/components/ImageLeft.vue'
import VideoLeft from '~/components/VideoLeft.vue'
import TallCopySmall from '~/components/TallCopySmall.vue'
import CopyLeft from '~/components/CopyLeft.vue'
import DoubleCopy from '~/components/DoubleCopy.vue'
import WorkingTogetherCta from '~/components/WorkingTogetherCta.vue'
import ProjectsCta from '~/components/ProjectsCta.vue'

export default {
  name: "Project",

  components: {
    Intro,
    FullImage,
    DoubleImage,
    TripleImage,
    ImageLeft,
    VideoLeft,
    TallCopySmall,
    DoubleCopy,
    CopyLeft,
    WorkingTogetherCta,
    ProjectsCta,
  },
}
</script>

<page-query>
query Project($path: String) {
  project(path: $path) {
    id
    slug
    path
    title
    titlePart1
    titlePart2
    contributors {
      label
      name
    }
    intro
    sections {
      id
      type
      isReversed
      isUpsidedown
      heading
      copy
      copy1
      copy2
      image
      image1
      image2
      image3
      video
    }
  }
  projects: allProject(sortBy: "id", order: ASC) {
    edges {
      node {
        id
        title
        path
        thumbnail
      }
    }
  }
}
</page-query>
