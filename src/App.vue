<template>
  <div id="app" class="body" data-state>

		<transition name="fade" mode="out-in">
			<router-view :key="$route.fullPath"></router-view>
		</transition>

  </div>
</template>


<script>
export default {
  components: {
    
  },
}
</script>


<style lang="css">
  @font-face {
    font-family: "Museo";
    src: url("./assets/fonts/museo-sans-500.woff") format('woff');
    font-weight: 500;
  }

  .fade-enter-active, .fade-leave-active {
    transition-property: opacity;
    transition-duration: 300ms;
  }

  .fade-enter-active {
    transition-delay: 300ms;
  }

  .fade-enter, .fade-leave-active {
    opacity: 0
  }
</style>