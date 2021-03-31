<template>

	<section class="frame trim gutter" appear="fade-up">
		<div class="sm:gutter">
			<div class="inner">
				<blockquote class="quotator" :style="`min-height: ${minQuoteHeight}px;`">
					<div 
						class="quotator__block"
						v-for="(quote, index) in quoteBlocks" 
						:key="`quotator-${index}`" 
						:style="`opacity: ${currentQuoteIndex == index ? 1 : 0}; 
										transform: scale(${currentQuoteIndex == index ? 1 : 0.98});`">
						<div class="quotator__icon"></div>
						<div class="quotator__copy">
							<p class="quotator__quote">{{ quote.copy }}</p>
							<cite class="quotator__cite">{{ quote.cite }}</cite>
						</div>
					</div>
				</blockquote>
			</div>
		</div>
	</section>

</template>


<script>
export default {
	name: 'QuoteRotator',

  data() {
    return {
      currentQuoteIndex: 0,
			minQuoteHeight: 200,
      quoteBlocks: [
        { 
					copy: "Thank you again for the superlative work that you and all your crew did to create our gorgeous home. It’s been a pleasure working with you and of course we won’t hesitate to recommend you to our friends",
					cite: "Gale Musker", 
				},
        { 
					copy: "Thank you so much for the fantastic job on our new suite. We’re so happy with how it all came out. We truly appreciate your hard work and the care that it took to make it all work. We have already had visitors and it made their stay much more enjoyable since we have so much room.", 
					cite: "Caroline and John Fuller", 
				},
			],
    }
	},
	
	methods: {
		quoteSwapper() {
			var intervalId = setInterval( () => {
				this.currentQuoteIndex = this.loopUpCurrentIndex(this.currentQuoteIndex)
			}, 8000);
		},

		loopUpCurrentIndex( num ) {
			num === this.quoteBlocks.length-1 ? num = 0 : num++
			return num
		},

		setMinHeightForQuote() {
			let quoteBlocks = document.querySelectorAll(".quotator__block")
			let tallestQuote = 0
			quoteBlocks.forEach( quote => {
				if ( quote.offsetHeight > tallestQuote ) {
					tallestQuote = quote.offsetHeight
				}
			})
			this.minQuoteHeight = tallestQuote
		},
	},

	mounted() {
		this.setMinHeightForQuote()
		this.quoteSwapper()
    
    window.addEventListener( 'resize', () => {
			this.setMinHeightForQuote()
    });
	}
}
</script>