<template>
  <Layout class="layout-about">

    <intro
      top-title="About Us">
      <p slot="copy">
        Newhaven Builders is a company that prides itself on achieving client objectives, on time and on budget through a purposeful corporate culture of integrity, craftsmanship and drive. We are proud that many of our employees have been with us 30 years and are well experienced tradesmen and supervisors. Such cohesiveness allows us an efficient management structure that time over, meets client benchmarks and exceeds expectations. 
      </p>
    </intro>

    <full-image :data="fullImage1">
      <g-image class="w-full" src="~/assets/santiago-large-01.jpg" />
    </full-image>

    <ken-rideout />

    <full-image :data="fullImage2">
      <g-image class="w-full" src="~/assets/la-loma-large.jpg" />
    </full-image>

    <our-mission />

    <full-image :data="fullImage3">
      <g-image class="w-full" src="~/assets/mar-vista-large.jpg" />
    </full-image>

    <copy-and-double-list :data="copyLists1" />

    <full-image :data="fullImage4">
      <g-image class="w-full" src="~/assets/santiago-large-02.jpg" />
    </full-image>

    <copy-and-double-list :data="copyLists2" />

    <working-together-cta />

  </Layout>
</template>

<script>
import Intro from '~/components/Intro.vue'
import FullImage from '~/components/FullImage.vue'
import CopyAndDoubleList from '~/components/CopyAndDoubleList.vue'
import OurMission from '~/components/OurMission.vue'
import WorkingTogetherCta from '~/components/WorkingTogetherCta.vue'
import KenRideout from '~/components/KenRideout.vue'

export default {
  metaInfo: {
    title: 'About Us'
  },
  
  components: {
    Intro,
    FullImage,
    CopyAndDoubleList,
    OurMission,
    WorkingTogetherCta,
    KenRideout,
  },
	
	data() {
    return {
      fullImage1: {
        id: "fullImage1",
      },
      fullImage2: {
        id: "fullImage2",
      },
      fullImage3: {
        id: "fullImage3",
      },
      copyLists1: {
        id: "copyLists1",
        heading: "Experience",
        copy: "With 30 years and over 300 homes under our belt, we've worked with some of today's great architects and designers. In addition, we've had the privilege of working on many historically significant homes, including those designed by the following acclaimed architects.",
        list1: [
          "Louis B. Easton",
          "Marla Felber",
          "Charles And Henry Greene",
          "Buff & Hensman",
          "Arthur B Alfred S. Heineman",
          "Myron Hunt",
          "Reginald B. Johnson",
          "Georgie Kajer",
          "Liza Kerrigan",
        ],
        list2: [
          "Sylvanus Marston",
          "Susan Masterman",
          "Kelly Sutherlin McLeod",
          "Wallace Neff",
          "Harlan Pedersen",
          "Garret Van Pelt",
          "George Washington Smith",
          "Frank Lloyd Wright",
          "Frank Lloyd Wright Jr.",
        ],
      },
      fullImage4: {
        id: "fullImage4",
      },
      copyLists2: {
        id: "copyLists2",
        heading: "Style",
        copy: "As builders, we love the art of taking something historical, then adding on to it in such a way one can’t tell where new house began and original house ended…equally difficult, building a new, custom home in a way that honors the style's history, yet appropriately bridges the materials and conveniences of today. Modern to Victorian, we are well versed.",
        list1: [
          "Queen Anne Victorian",
          "Victorian Farmhouse",
          "Arts & Crafts",
          "Craftsman",
          "Colonial Revival",
          "Mission Revival",
          "Greek Revival",
          "Dutch Colonial Revival",
        ],
        list2: [
          "Mediterranean Renaissance",
          "Spanish Colonial",
          "Prairie Style",
          "English Tudor / Cotswald",
          "Contemporary / Modern",
          "Mid-century Post And Beam",
        ],
      },
    }
  },
}
</script>
