<template>
	<section :id="data.id" class="frame sm:gutter">
		<div class="outer flex flex-col md:flex-row">
			<figure class="trim pt-0 md:pb-0" appear="fade-up">
				<g-image class="w-full" :src="data.image1" />
			</figure>
			<figure class="md:gutter pr-0" appear="fade-up">
				<g-image class="w-full" :src="data.image2" />
			</figure>
		</div>
	</section>
</template>


<script>
export default {
	name: 'DoubleImage',
		
	props: {
		data: Object,
	},
}
</script>