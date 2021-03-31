<template>
	<section class="sm:gutter">
		<g-link 
			class="project-card trim wrapper" 
			:class="isHovering && hoverIndex === index ? enterClass : leaveClass"
			v-for="(project, index) in $page.projects.edges" 
			:key="project.node.id" 
			:to="project.node.path"
			@mouseover.native="isHovering = true, hoverIndex = index"
			@mouseleave.native="isHovering = false">

			<figure class="project-card__column project-card__figure" appear="fade-up">
				<div class="cover" :style="`padding-top: ${project.node.featImageAspect};`">
					<g-image class="cover__figure project-card__image" :src="project.node.featImage" />
				</div>
				<figcaption class="project-card__caption caption gutter">{{ project.node.featCaption }}</figcaption>
			</figure>

			<div class="project-card__column project-card__content" appear="fade-up" appear-delay="300">
				<div class="project-card__copy gutter">
					<h3 class="project-card__heading">{{ project.node.title }}</h3>
					<p class=" mt-10">{{ project.node.excerpt }}</p>
					<div class="accent-fork accent-fork--left mt-10">
						<div class="accent-fork__plus"></div>
					</div>
				</div>
			</div>

		</g-link>
	</section>
</template>


<script>
export default {
	name: 'ProjectCards',
	
	data() {
    return {
			isHovering: false,
			hoverIndex: null,
			enterClass: "fork-plus-hover",
			leaveClass: "fork-plus-leave",
    }
	},
}
</script>

<!--
Make sure to add this query to the page you are using this component

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
-->