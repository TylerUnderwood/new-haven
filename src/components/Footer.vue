<template>
	<footer id="footer" class="footer trim gutter">
    <div class="footer__inner outer meta">

      <div class="footer__col footer__address f12 md:f14">
        <span class="name">Newhaven Builders</span>

        <address class="address mt-4">
          Los Angeles, CA
        </address>

        <a class="footer__link phone-number mt-4" href="tel:626.798.9880">
          626.798.9880
        </a>

        <a class="footer__link email mt-4" href="mailto:info@newhavenbuilders.com">
          info@newhavenbuilders.com
        </a>
      </div>

      <div class="footer__col footer__deco">
        <g-image 
          class="footer__image" 
          src="~/assets/svg/footer-deco-1.svg" 
          alt="Deco Accent" 
          v-if="currentDeco == 0" />
        <g-image 
          class="footer__image" 
          src="~/assets/svg/footer-deco-2.svg" 
          alt="Deco Accent" 
          v-if="currentDeco == 1" />
        <g-image 
          class="footer__image" 
          src="~/assets/svg/footer-deco-3.svg" 
          alt="Deco Accent" 
          v-if="currentDeco == 2" />
        <g-image 
          class="footer__image" 
          src="~/assets/svg/footer-deco-4.svg" 
          alt="Deco Accent" 
          v-if="currentDeco == 3" />
      </div>

      <div class="footer__col footer__navs">
        <nav class="footer__nav nav f16">
          <g-link 
            class="nav__link link" 
            v-for="navLink in navLinks"
            :key="navLink.index" 
            :to="navLink.link">
            {{ navLink.text }}
          </g-link>
        </nav>
        <nav class="footer__nav nav mt-2 f12 sm:f14">
          <g-link 
            class="nav__link link grey" 
            v-for="subnavLink in subnavLinks"
            :key="subnavLink.index" 
            :to="subnavLink.link">
            {{ subnavLink.text }}
          </g-link>
        </nav>
      </div>

      <div class="footer__col footer__copyright f12">
        <span class="copyright">
          Copyright {{ currentYear }}. All rights reserved
        </span>

        <a class="footer__link signature mt-2" href="https://statebuilt.com/">
          Site by State
        </a>
      </div>

    </div>
	</footer>
</template>


<script>
export default {
  name: 'Footer',

  data() {
    return {
      currentYear: new Date().getFullYear(),
      currentDeco: 0,
      navLinks: [
        {
          text: "Home",
          link: "/",
        },
        {
          text: "About",
          link: "/about/",
        },
        {
          text: "Our Process",
          link: "/our-process/",
        },
        {
          text: "Contact",
          link: "/contact/",
        },
      ],
      subnavLinks: [
        {
          text: "Contractor Resources",
          link: "/resources-contractor",
        },
        {
          text: "Client Portal",
          link: "https://NewhavenBuilders.coconstruct.com",
        },
      ],
    }
  },

  methods: {
    randomDecoNumber() {
      this.currentDeco = this.getRandomInt(4)
    },

    getRandomInt(max) {
      return Math.floor(Math.random() * Math.floor(max));
    },
  },

  mounted() {
    this.randomDecoNumber()
  }
}
</script>