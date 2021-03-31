<template>
	<section :id="data.id" class="frame gutter">
		<div class="outer flex flex-col" :class="rowClass">
			<div class="md:w-1/2 lg:w-2/3 md:gutter" :class="gutterClass" appear="fade-up">
				<!-- {{ data.video }} -->
				<div class="embed-frame">
					<iframe title="vimeo-player" src="https://player.vimeo.com/video/90917361" width="640" height="360" frameborder="0" allowfullscreen></iframe>
				</div>
			</div>
			<div class="md:w-1/2 lg:w-1/3" appear="fade-up" appear-delay="300">
				<div class="pt-12 md:pb-12" v-if="data.heading && data.copy">
					<h3 class="mb-10">
						{{ data.heading }}
					</h3>
					<p>{{ data.copy }}</p>
					<div class="accent-fork accent-fork--left mt-10">
						<div class="accent-fork__base"></div>
					</div>
				</div>
			</div>
		</div>
	</section>
</template>


<script>
export default {
	name: 'VideoLeft',

	data() {
    return {
			rowClass: this.data.isReversed ? 'md:flex-row-reverse' : 'md:flex-row',
			gutterClass: this.data.isReversed ? 'pr-0' : 'pl-0',
    }
	},

	props: {
		data: Object,
	},
}
</script>


<style lang="scss" scoped>
.embed-frame {
	position: relative;
	display: block;
	width: 100%;
	padding: 0;
	overflow: hidden;

	&::before {
		display: block;
		padding-top: 56.25%;
		content: '';
	}

	iframe {
		position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: 0;
	}
}
</style>