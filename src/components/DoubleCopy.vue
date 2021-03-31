<template>
	<section :id="data.id" class="frame trim gutter">
		<div class="outer sm:gutter">
			<div class="inner">
				<h4 class="mb-10" appear="fade-up" :appear-group="data.id">{{ data.heading }}</h4>
				<div class="flex flex-col md:flex-row mt-8">

					<div class="mxw-copy" appear="fade-up" :appear-group="data.id">
						<p>{{ data.copy1 }}</p>
					</div>

					<div class="gap"></div>
					<div class="gap"></div>

					<div class="mxw-copy" appear="fade-up" :appear-group="data.id">
						<p>{{ data.copy2 }}</p>
					</div>

					<div class="gap"></div>
					<div class="gap"></div>

					<div appear="fade-up" :appear-group="data.id">
						<div class="accent-fork accent-fork--down hide lg:show">
							<div class="accent-fork__base"></div>
						</div>
						<div class="accent-fork accent-fork--left md:hide">
							<div class="accent-fork__base"></div>
						</div>
					</div>

				</div>
			</div>
		</div>
	</section>
</template>


<script>
export default {
	name: 'DoubleCopy',
		
	props: {
		data: Object,
	},
}
</script>