<template>

	<section id="intro" class="frame trim gutter">
		<div class="inner">

			<page-title :topTitle="topTitle" :bottomTitle="bottomTitle" />

		</div>

		<div class="outer sm:gutter frame mb-0">

			<div class="inner flex flex-col md:flex-row">
				<div class="md:w-1/2 flex md:pr-8" :class="hasInfoClass" appear="fade-up" appear-group="intro">

					<slot name="info"></slot>

					<div class="hide md:show ml-auto pl-8">
						<div class="accent-fork accent-fork--down" appear="fade-up" appear-group="intro">
							<div class="accent-fork__base"></div>
						</div>
					</div>
				</div>
				<div class="md:w-1/2" :class="hasInfoCopyClass" appear="fade-up" appear-group="intro">

					<div class="mxw-copy">
						<slot name="copy"></slot>
					</div>

					<div class="accent-fork accent-fork--left mt-6 md:hide">
						<div class="accent-fork__base"></div>
					</div>
				</div>
			</div>

		</div>
	</section>

</template>


<script>
import PageTitle from './PageTitle.vue';

export default {
	name: 'Intro',

  props: {
		topTitle: String,
		bottomTitle: String,
	},

	components: {
		PageTitle,
	},

	data() {
    return {
			hasInfoClass: null,
			hasInfoCopyClass: null,
		}
	},

	computed: {
    hasInfoSlot () {
      return !!this.$slots[ "info" ] || !!this.$scopedSlots[ "info" ];
    }
	},

	mounted() {
		this.hasInfoClass = this.hasInfoSlot ? "md:pr-10" : null
		this.hasInfoCopyClass = this.hasInfoSlot ? "frame md:mt-0 mb-0" : null
	}
}
</script>