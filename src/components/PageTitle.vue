<template>
  <h1 class="page-title">
    <span 
      class="page-title__top" 
      appear="fade-right" 
      appear-group="intro">
      {{ topTitle }}
    </span>
    <span 
      v-if="bottomTitle" 
      class="page-title__bottom buffer mr-0" 
      appear="fade-left" 
      appear-group="intro">
      {{ bottomTitle }}
    </span>
  </h1>
</template>


<script>
export default {
	name: 'PageTitle',

  props: {
		topTitle: String,
		bottomTitle: String,
	},
}
</script>