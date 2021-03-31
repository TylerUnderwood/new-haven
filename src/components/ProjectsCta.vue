<template>
	<section class="project-cta frame trim sm:gutter">
		<div class="project-cta__inner wrapper">

			<div class="project-cta__column project-cta__figure" appear="fade-up">
				<div class="project-cta__label gutter sm:pl-0 sm:pr-0">
					<div class="caption">Projects</div>
				</div>
				<figure class="project-cta__image">
					<div class="cover" style="padding-top: 64%">
						<transition-group name="fade">
							<template v-for="(project, index) in $page.projects.edges">
								<g-image 
									class="cover__figure w-full" 
									v-if="hoveredLinkIndex === index" 
									:src="project.node.thumbnail" 
									:key="`project-thumb-${index}`" />
							</template>
						</transition-group>
					</div>
				</figure>
			</div>

			<div class="project-cta__column project-cta__content trim pb-0 gutter md:pr-0">
				<div class="project-cta__list">
					<nav class="fancy-nav">
						<g-link 
							class="fancy-nav__link" 
							v-for="(project, index) in $page.projects.edges" 
							:key="`project-title-${index}`" 
							:to="project.node.path"
							appear="fade-left"
							:appear-delay="`${index + 1}00`"
							@mouseover.native="hoveredLinkIndex = index"
							@mouseleave.native="hoveredLinkIndex = getDefaultHover()">
							<span class="fancy-nav__text">{{ project.node.title }}</span>
						</g-link>
					</nav>
					<div class="mt-10" appear>
						<g-link class="deco-button flex items-center link has-hover-icon" :to="nextLink">
							<div class="mr-4">
								<icon-next/>
							</div>
							<span class="caption f18">Next</span>
						</g-link>
					</div>
				</div>
			</div>

		</div>
	</section>
</template>


<script>
import IconNext from './icons/IconNext.vue'

export default {
	name: 'ProjectsCta',

  components: {
		IconNext,
	},
	
	data() {
    return {
			nextLink: "",
			hoveredLinkIndex: 0,
			currentProjectIndex: 0,
			isProjectPage: false,
    }
	},

	methods: {
		loopUp( num ) {
			let lastNodeIndex = this.$page.projects.edges.length-1
			num === lastNodeIndex ? num = 0 : num++
			return num
		},

		setCurrentIndex() {
			if ( this.isProjectPage ) {	
				// get the current project ID
				const currentId = this.$page.project.id
				// function to match the current ID
				const isCurrentId = (project) => project.node.id == currentId;
				// loop through projects to find matching ID
				const currentIndex = this.$page.projects.edges.findIndex(isCurrentId)
				// set the current project index
				this.currentProjectIndex = currentIndex
			}
		},

		getDefaultHover() {
			return this.isProjectPage ? this.currentProjectIndex : 0;
		},

		setDefaultHover() {
			this.hoveredLinkIndex = this.getDefaultHover()
		},

		getNextIndex() {
			return this.loopUp( this.currentProjectIndex )
		},

		setNextPath() {
			let nextIndex = this.isProjectPage ? this.getNextIndex() : 0;
			let nextPath = this.$page.projects.edges[nextIndex].node.path;

			this.nextLink = nextPath;
		},
	},

  mounted() {
		this.isProjectPage = !!this.$page.project
		this.setCurrentIndex()
		this.setDefaultHover()
		this.setNextPath()
  },
}
</script>


<style scoped>

.fade-enter-active, 
.fade-leave-active {
	transition-property: opacity;
  transition-duration: 1000ms;
  transition-timing-function: cubic-bezier(.29,.4,.15,.91);
}
.fade-enter, 
.fade-leave-to {
  transition-delay: 300ms;
  opacity: 0;
}

</style>


<!--
Make sure to add this query to the page you are using this component

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
-->