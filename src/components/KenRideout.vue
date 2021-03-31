<template>

	<section class="frame gutter">
		<div class="outer section section--reverse">
			<div class="section__column section__half trim gutter" appear="fade-up" appear-delay="300">
				<div class="section__wrap md:gutter inner--half">
					<div class="mxw-copy">
						<h3 class="mb-10">Building With Trust And Respect</h3>
						<p>Ken Rideout is the creative force behind Newhaven Builders, recognized for his keenness interpreting the client's objectives and translating them into experiences that impact the senses. Ken's design skills were nurtured from childhood, eventually leading to his passion for building. Years of field experience have honed him into a Master Carpenter and in the 90's, Ken founded Newhaven Builders. Setting him apart is a unique blend of talents for design, communication, and an acute problem solving ability. Overall, what drives Ken is to see a client's vision turn into their dream home.</p>
						<div class="accent-fork accent-fork--left mt-10">
								<div class="accent-fork__base"></div>
						</div>
					</div>
				</div>
			</div>
			<div class="section__column section__half" appear="fade-up">
				<div class="section__block">
					<figure class="seciton__wrap lg:gutter pr-0">
						<g-image class="w-full mb-4" src="~/assets/ken-rideout.jpg" />
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
		</div>
	</section>

</template>


<script>
export default {
    name: 'KenRideout',
}
</script>