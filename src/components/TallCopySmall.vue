<template>
	<section :id="data.id" class="frame sm:gutter">
		<div class="outer flex flex-col" :class="rowClass">
			<div class="md:w-1/2 lg:w-3/5 md:gutter" :class="imageClass" appear="fade-up">
				<g-image class="w-full" :src="data.image1" />
			</div>
			<div class="md:w-1/2 lg:w-2/5 flex flex-col" :class="columnClass">
				<div 
					class="trim flex-grow gutter md:pr-0 md:pl-0 frame md:mt-0 md:mb-0" 
					:class="copyClass" 
					appear="fade-up" 
					appear-delay="300"
					v-if="data.heading && data.copy">
					<h3 class="mb-10">
						{{ data.heading }}
					</h3>
					<p class="mxw-copy">{{ data.copy }}</p>
					<div class="accent-fork accent-fork--left mt-10">
						<div class="accent-fork__base"></div>
					</div>
				</div>
				<figure appear="fade-up" :class="hasCopyClass">
					<g-image class="w-full" :src="data.image2" />
				</figure>
			</div>
		</div>
	</section>
</template>


<script>
export default {
	name: 'TallCopySmall',
		
	props: {
		data: Object,
	},

	data() {
    return {
			rowClass: this.data.isReversed ? 'md:flex-row-reverse' : 'md:flex-row',
			imageClass: this.data.isReversed ? 'pr-0' : 'pl-0',
			columnClass: this.data.isUpsidedown ? 'md:flex-col-reverse' : null,
			copyClass: this.data.isUpsidedown ? 'md:pb-0' : null,
			hasCopyClass: this.data.heading && this.data.copy ? null : 'frame mb-0 md:mt-0'
    }
	},
}
</script>