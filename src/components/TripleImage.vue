<template> 
	<section :id="data.id" class="frame sm:gutter">
		<div class="outer triple-image">
			<div class="triple-image__tall md:buffer ml-0" appear="fade-up" :appear-group="data.id">
				<g-image class="w-full" :src="data.image1" />
			</div>
			<div class="triple-image__double">
				<figure class="image-overflow triple-image__top frame mb-0 md:m-0" appear="fade-up" :appear-group="data.id">
					<g-image class="w-full" :src="data.image2" />
				</figure>
				<figure class="image-overflow triple-image__bottom frame mb-0" appear="fade-up" :appear-group="data.id">
					<g-image class="w-full" :src="data.image3" />
				</figure>
			</div>
		</div>
	</section>
</template>


<script>
export default {
	name: 'TripleImage',
		
	props: {
		data: Object,
	},
}
</script>