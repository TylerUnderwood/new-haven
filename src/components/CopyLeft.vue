<template>
	<section :id="data.id" class="frame trim gutter">
		<div class="outer sm:gutter">
			<div class="inner flex flex-col" :class="rowClass">

				<div class="flex-1"></div>

				<div class="md:w-2/3 mxw-copy" appear="fade-up">
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
	name: 'CopyLeft',

	props: {
		data: Object,
	},

	data() {
    return {
			rowClass: this.data.isReversed ? 'md:flex-row-reverse' : 'md:flex-row',
    }
	},
}
</script>