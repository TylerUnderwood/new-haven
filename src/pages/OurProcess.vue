<template>
  <Layout class="layout-info">

    <intro
      top-title="Working"
      bottom-title="Together">
      <p slot="copy">
        Luxury, beauty, and deep craftsmanship are hallmarks of our builds. Our projects are not simply beautiful, but also functional, giving you a sense of freedom within your home. We know the construction process can be overwhelming; a good builder understands this and will advocate for their client's needs and desires. It's essential for creating trust. Better communication always results in better builds.
      </p>
    </intro>

    <section class="frame gutter">
      <div class="inner flex flex-col-reverse md:flex-row">

        <div class="md:w-1/2 md:gutter pl-0 md:mb-0 flex">
          <div class="w-full trim lg:pt-0 pb-0">

            <div class="lg:mxw-copy sm:gutter md:pl-0 md:pr-0">
              <h4 class="mb-8" appear="fade-left">Design + Build</h4>
              <p appear="fade-left">Sometimes clients have a specific architect in mind they plan to work with, while other times newhaven will perform both design and build services. Every situation is different. If you are looking for unique design coupled with equally quality construction, our design + build services offer a bespoke product that produces a luxury build as unique as you.</p>
              <div class="accent-fork accent-fork--left mt-8">
                <div class="accent-fork__base"></div>
              </div>
            </div>

          </div>
        </div>
        <div class="md:w-1/2 flex flex-col align-end md:gutter pr-0">

          <figure class="md:mxw-copy" appear="fade-right">
            <g-image class="w-full" src="~/assets/blueprint-square.jpg" />
          </figure>

        </div>
      </div>
    </section>

    <section class="frame trim gutter">
      <div class="inner flex flex-col md:flex-row sm:gutter md:pl-0 md:pr-0">
        <div class="md:w-1/2 mxw-copy">
          <ul class="simple-list" appear="fade-up" appear-group="list1">
            <li>Client Vision Meetings</li>
            <li>Existing Conditions Verification</li>
            <li>Preliminary Design Drawings</li>
          </ul>
        </div>
        <div class="md:w-1/2 mxw-copy mt-4 md:mt-0">
          <ul class="simple-list" appear="fade-up" appear-group="list1">
            <li>Design Concept Creation</li>
            <li>Proposed Scope Of Work</li>
            <li>Preliminary Budget Development</li>
          </ul>
        </div>
      </div>
    </section>

    <section class="frame gutter">
      <div class="inner flex flex-col lg:flex-row">
        <div class="lg:w-1/2">

          <div class="flex flex-col-reverse md:flex-row">
            <div class="md:w-1/2 lg:w-full trim lg:pt-0 pb-0 md:gutter pl-0">
              <div class="lg:mxw-copy sm:gutter md:pl-0 md:pr-0">
                <h4 class="pt-0 mb-8" appear="fade-left">Construction</h4>
                <p appear="fade-left">Taking what an architect or designer has been entrusted with and then build to specification. At its core, that's good construction. Great construction is delivering on the previous with quality that exceeds expectations and transparent, effective management driving the project to run seamlessly.</p>
              </div>
            </div>

            <figure class="md:w-1/2 lg:hide md:gutter pr-0" appear="fade-right">
              <g-image class="w-full" src="~/assets/construct.jpg" />
            </figure>
          </div>

          <div class="flex lg:mxw-copy frame mb-0 trim lg:pt-0 pb-0 sm:gutter md:pl-0 md:pr-0">
            <ul class="icon-list">
              <li 
                class="icon-list__item" 
                appear="fade-left" 
                v-for="(item, index) in iconList" 
                :key="index">
                <div class="icon-list__figure">
                  <g-image v-if="index == 0" src="~/assets/svg/deco-icon-1.svg" alt="Icon" />
                  <g-image v-if="index == 1" src="~/assets/svg/deco-icon-2.svg" alt="Icon" />
                  <g-image v-if="index == 2" src="~/assets/svg/deco-icon-3.svg" alt="Icon" />
                  <g-image v-if="index == 3" src="~/assets/svg/deco-icon-4.svg" alt="Icon" />
                </div>
                <div class="icon-list__content">
                  <h4 class="large">{{ item.heading }}</h4>
                  <p class="small">{{ item.copy }}</p>
                </div>
              </li>
            </ul>
          </div>

        </div>
        <div class="frame lg:mt-0 mb-0 lg:w-1/2 trim lg:pt-0 lg:pb-0 lg:gutter pr-0">

          <figure class="mxw-copy hide lg:show" appear="fade-right">
            <g-image class="w-full" src="~/assets/construct.jpg" />
          </figure>

          <div class="mxw-640 lg:frame mb-0 sm:gutter md:pl-0 md:pr-0">
            <ul class="simple-list" appear="fade-up">
              <li>Estimating Services</li>
              <li>Materials Consulting</li>
              <li>Online Management Portal</li>
              <li>Project Scheduling</li>
              <li>Project Budget</li>
              <li>Quality Control / On-site Supervision</li>
              <li>Subcontractor Management</li>
              <li>On-site Meetings With Owner / Architect / Designer</li>
              <li>Clean Job Sites, Professional Attitudes</li>
            </ul>
          </div>
        
        </div>
      </div>
    </section>

    <section class="frame trim pb-0 gutter">
      <div class="outer section sm:gutter md:pl-0 md:pr-0">
        <div class="section__column section__half">
          <div class="section__wrap inner--half">
            <figure class="mxw-640 mr-auto" appear="fade-right">
              <g-image class="w-full mb-4" src="~/assets/ken-rideout-square.jpg" />
              <div class="flex">
                <div class="block">
                  <figcaption class="caption">Ken Rideout</figcaption>
                  <span class="meta tiny">Founder</span>
                </div>
                <div class="filler"></div>
                <g-link 
                  class="icon-link meta tiny accent-color" 
                  to="/resources/ken_rideout_resume.pdf" 
                  target="_blank">
                  <span class="icon">
                    <g-image src="~/assets/svg/resume-icon.svg"></g-image>
                  </span>
                  <span class="text ml-1">Resume</span>
                </g-link>
              </div>
            </figure>
          </div>
        </div>
        <div class="section__column section__half trim gutter" appear="fade-left">
          <div class="section__wrap gutter">
            <div class="flex flex-col justify-center items-center mxw-copy">
              <blockquote class="big-quote">Great work comes through effective relationships. We make the building process enjoyable, trusting and professional.</blockquote>
              <div class="accent-fork accent-fork--right mt-8 self-start">
                <div class="accent-fork__base"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <our-mission />

    <full-image :data="fullImage1">
      <g-image class="w-full" src="~/assets/mar-vista-large.jpg" />
    </full-image>

    <copy-and-double-list :data="copyLists1" />

    <quote-rotator />

    <full-image :data="fullImage2">
      <g-image class="w-full" src="~/assets/santiago-large-02.jpg" />
    </full-image>

    <copy-and-double-list :data="copyLists2" />

    <projects-cta />

    <contact-cta />

  </Layout>
</template>

<script>
import Intro from '~/components/Intro.vue'
import FullImage from '~/components/FullImage.vue'
import CopyAndDoubleList from '~/components/CopyAndDoubleList.vue'
import QuoteRotator from '~/components/QuoteRotator.vue'
import OurMission from '~/components/OurMission.vue'
import ProjectsCta from '~/components/ProjectsCta.vue'
import ContactCta from '~/components/ContactCta.vue'

export default {
  metaInfo: {
    title: 'Working Together'
  },

  components: {
    Intro,
    FullImage,
    CopyAndDoubleList,
    QuoteRotator,
    OurMission,
    ProjectsCta,
    ContactCta,
  },

  data() {
    return {
      fullImage1: {
        id: "fullImage1",
      },
      iconList: [
        {
          heading: "New Homes",
          copy: "Build your vision from scratch, the ground up with the highest standards throughout.",
        },
        {
          heading: "Remodels and Additions",
          copy: "Increase your homes footprint, readapt and reimagine a space to meet your needs.",
        },
        {
          heading: "Restorations",
          copy: "Bring a cultural heritage back to life through sustainable preservation and materials conservation while appropriately graphing in all of today's modern conveniences.",
        },
        {
          heading: "Custom Projects",
          copy: "Providing clients with a solution to build out high-end details, specifically finish carpentry; our crew is recognized as the best in high-end finish carpentry within the greater los angeles area.",
        },
      ],
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
      fullImage2: {
        id: "fullImage2",
      },
      copyLists2: {
        id: "copyLists2",
        heading: "Style",
        copy: "As builders, we love the art of taking something historical then adding on to it in such a way one can’t tell where new house began and original house ended… equally difficult, building a new, custom home in way that honors the styles history, yet appropriately bridges the materials and conveniences of today. Modern to Victorian, we are well versed.",
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

<page-query>
  query Home {
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
