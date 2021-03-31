<template>
	<section :id="data.id" class="frame sm:gutter">
		<div class="outer flex flex-col" :class="rowClass">
			<div class="md:w-1/2 lg:w-2/3" appear="fade-up">
				<figure class="md:gutter" :class="imageClass" v-if="data.image">
					<g-image class="w-full" :src="data.image" />
				</figure>
			</div>
			<div class="md:w-1/2 lg:w-1/3" appear="fade-up" appear-delay="300">
				<div class="trim gutter md:pl-0 md:pr-0" v-if="data.heading && data.copy">
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
	name: 'ImageLeft',

	props: {
		data: Object,
	},

	data() {
    return {
			rowClass: this.data.isReversed ? 'md:flex-row-reverse' : 'md:flex-row',
			imageClass: this.data.isReversed ? 'pr-0' : 'pl-0',
    }
	},
}
</script>