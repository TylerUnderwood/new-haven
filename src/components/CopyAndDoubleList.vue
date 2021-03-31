<template>
	<section :id="data.id" class="frame gutter">
    <div class="outer pt-10 pb-10 sm:gutter">
      <div class="inner">
        <h4 appear="fade-up">{{ data.heading }}</h4>
        <div class="flex flex-col lg:flex-row mt-8">
          <div class="mxw-copy" appear="fade-up" :appear-group="`${data.id}`">
            <p>{{ data.copy }}</p>
          </div>
          <div class="flex flex-col md:flex-row mt-10 lg:m-0">
            <div class="lg:pl-10 xl:pl-16" appear="fade-up" :appear-group="`${data.id}`">
              <ul class="simple-list">
                <li v-for="(text, index) in data.list1" :key="`${data.id}-list1-${index}`">{{ text }}</li>
              </ul>
            </div>
            <div class="md:pl-10 xl:pl-16 mt-6 md:m-0">
              <ul class="simple-list" appear="fade-up" :appear-group="`${data.id}`">
                <li v-for="(text, index) in data.list2" :key="`${data.id}-list2-${index}`">{{ text }}</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>


<script>
export default {
  name: 'CopyAndDoubleList',

	props: {
		data: Object,
	},
}
</script>