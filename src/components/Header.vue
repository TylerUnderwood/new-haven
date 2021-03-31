<template>
  <header id="header" class="header gutter" :class="menuState" appear="fade-down">
    <div class="header__inner">
      <div class="header__col header__back">
        <g-link class="back-button flex items-center link has-hover-icon" to="/">
          <div class="mr-4 back-button__img">
            <icon-back/>
          </div>
          <span class="back-button__text caption">Back</span>
        </g-link>
      </div>
      <div class="header__col header__logo">
        <g-link id="logo" class="logo" to="/">
          <g-image class="logo__img" src="~/assets/svg/logo.svg" />
        </g-link>
      </div>
      <div class="header__col header__menu">
        <button class="menu-button flex items-center" @click.prevent="toggleNav">
          <div class="menu-button__icon">
            <span class="bar"></span>
            <span class="bar"></span>
            <span class="bar"></span>
          </div>
          <span class="menu-button__text ml-2">Menu</span>
        </button>
      </div>
    </div>
    <div class="menu gutter" v-show="menuIsActive">

      <button class="menu__close" @click.prevent="toggleNav">
        <g-image class="menu-button__img" src="~/assets/svg/icon-x-thin.svg" />
      </button>
      <div class="menu__buffer">
        <div class="menu__inner">
          <nav class="menu__nav">
            <g-link 
              class="menu__link" 
              v-for="menuLink in menuLinks" 
              :key="menuLink.index" 
              :to="menuLink.link"
              :target="menuLink.isBlank ? '_blank' : null">
              <div class="menu__link__icon">
                <g-image class="menu-button__img" src="~/assets/svg/arrow-left.svg" />
              </div>
              <span class="menu__link__text">{{ menuLink.text }}</span>
            </g-link>
          </nav>
          <nav class="menu__subnav mt-4">
            <g-link 
              class="menu__link" 
              v-for="menuSubLink in menuSubLinks" 
              :key="menuSubLink.index" 
              :to="menuSubLink.link"
              :target="menuSubLink.isBlank ? '_blank' : null">
              <div class="menu__link__icon">
                <g-image class="menu-button__img" src="~/assets/svg/arrow-left.svg" />
              </div>
              <span class="menu__link__text">{{ menuSubLink.text }}</span>
            </g-link>
          </nav>
          <div class="menu__info flex flex-col mt-8">
            <span class="meta">Newhaven Builders</span>
            <span class="meta">Los Angeles, CA</span>
            <a class="meta veiled-link" href="tel:626.798.9880">Tel: 626.798.9880</a>
            <a class="meta veiled-link" href="mailto:info.newhavenbuilders.com">info.newhavenbuilders.com</a>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>


<script>
import IconBack from "./icons/IconBack.vue"

export default {
  name: 'Header',

  components: { 
    IconBack ,
  },

  data() {
    return {
      animationFinished: true,
      menuIsActive: false,
      menuState: 'menu-closed',
      menuLinks: [
        {
          text: "Home",
          link: "/",
        },
        {
          text: "Projects",
          link: "/projects/",
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
      menuSubLinks: [
        {
          text: "Ken’s Resume",
          link: "/resources/ken_rideout_resume.pdf",
          isBlank: true,
        },
        {
          text: "Contractor Resources",
          link: "/resources-contractor/",
        },
        {
          text: "Client Portal",
          link: "https://newhavenbuilders.coconstruct.com",
        },
      ],
    }
  },

  methods: {

    toggleNav() {
      if ( !this.menuIsActive && this.animationFinished ) {
        this.open();
      } 
      if ( this.menuIsActive && this.animationFinished ) {
        this.close();
      }
    },

    open() {
      this.$emit('menu-open');
      this.animationFinished = false;
      this.menuIsActive = true;
      this.menuOpening();
      setTimeout(() => {
        this.menuOpen();
        this.animationFinished = true;
      }, 640);
    },

    close() {
      this.$emit('menu-close');
      this.animationFinished = false;
      this.menuClosing();
      setTimeout(() => {
        this.menuClosed();
        this.menuIsActive = false;
        this.animationFinished = true;
      }, 640);
    },

    menuOpening() {
      document.body.classList.add('scroll-lock');
      document.body.classList.replace('menu-closed', 'menu-opening');
      this.menuState = 'menu-opening';
    },
    menuOpen() {
      document.body.classList.replace('menu-opening', 'menu-open');
      this.menuState = 'menu-open';
    },
    menuClosing() {
      document.body.classList.replace('menu-open', 'menu-closing');
      this.menuState = 'menu-closing';
    },
    menuClosed() {
      document.body.classList.remove('scroll-lock');
      document.body.classList.replace('menu-closing', 'menu-closed');
      this.menuState = 'menu-closed';
    },
  },

  mounted() {
    // when the page starts or refreshes, update the body
    document.body.classList.remove('menu-open');
    document.body.classList.remove('scroll-lock');
    document.body.classList.add('menu-closed');
  },
}
</script>