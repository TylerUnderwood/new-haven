<template>
	<section class="frame sm:gutter">
		<div class="wrapper flex flex-col-reverse md:flex-row">

			<div class="md:w-1/2 trim pb-0 flex md:justify-end">
				<div class="gutter md:pl-0 md:pr-0">
					<div class="inner--half md:gutter md:pl-0" appear="fade-up" appear-delay="300">
						<h4 class="mb-8">Reach Out</h4>
						<p>Start the project knowing your builder is advocating for your vision. Newhaven Builders has the processes and experience to deliver on a finished product that meets or exceeds expectations.</p>
						<g-link class="deco-button mt-8 flex items-center link has-hover-icon" to="/our-process/">
							<div class="mr-4">
								<icon-more/>
							</div>
							<span class="caption">Contact Us</span>
						</g-link>
					</div>
				</div>
			</div>

			<div class="md:w-1/2 flex justify-end" appear="fade-up">
				<figure class="w-full">
					<g-image src="~/assets/reachout.jpg" />
				</figure>
			</div>

		</div>
	</section>
</template>


<script>
import IconMore from "./icons/IconMore.vue"

export default {
	name: 'ContactCta',

  components: {
		IconMore
	},
}
</script>