<template> 
	<section :id="data.id" class="frame sm:gutter" appear="fade-up">
		<div class="outer">
			<g-image class="w-full" :src="data.image" v-if="data.image"/>
			<slot v-else />
		</div>
	</section>
</template>


<script>
export default {
	name: 'FullImage',
		
	props: {
		data: Object,
	},
}
</script>