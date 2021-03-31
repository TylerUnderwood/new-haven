<template>
  <Layout class="layout-contact">

    <intro
      top-title="Contact Us">
      <p slot="copy">
        Feel free to contact us for additional information, including official letters of recommendation and references. Building your dream home starts with one small email, we're highly approachable and look forward to hearing from you.
      </p>
    </intro>
    
    <section class="frame gutter">
      <div class="inner sm:gutter flex flex-col md:flex-row">
        <div class="md:w-3/5">

          <form
            name="contact"
            method="POST"
            v-on:submit.prevent="handleSubmit"
            action="/success"
            data-netlify="true"
            data-netlify-honeypot="bot-field"
          >
            <input type="hidden" name="contact-form" value="contact" />
            <div hidden>
              <label>
                Don’t fill this out: <input name="bot-field" />
              </label>
            </div>

            <div class="hold-focus js--hold-focus" appear="fade-right" appear-delay="300">
              <label class="label hold-focus__label" for="name">Name</label>
              <input class="hold-focus__input js--input-watch" id="name" type="text" name="name" v-model="formData.name" />
            </div>

            <div class="hold-focus js--hold-focus" appear="fade-right" appear-delay="400">
              <label class="label hold-focus__label" for="email">Email</label>
              <input class="hold-focus__input js--input-watch" id="email" type="email" name="email" v-model="formData.email" />
            </div>

            <div class="hold-focus js--hold-focus" appear="fade-right" appear-delay="500">
              <label class="label hold-focus__label" for="phone">Phone</label>
              <input class="hold-focus__input js--input-watch" id="phone" type="tel" name="phone" v-model="formData.phone" />
            </div>

            <div class="hold-focus js--hold-focus is-textarea" appear="fade-right" appear-delay="600">
              <label class="label hold-focus__label" for="message">Message</label>
              <textarea class="hold-focus__input js--input-watch" id="message" name="message" v-model="formData.message"></textarea>
            </div>

            <div appear="fade-right" appear-delay="700">
              <button class="btn mt-8" type="submit">Send</button>
            </div>
          </form>

        </div>
        <div class="md:w-2/5 trim md:pt-0 md:gutter pr-0">

          <div class="break" style="padding-top: 1.2rem;"></div>

          <div class="flex flex-col tiny" appear="fade-up">
            <span class="meta">Newhaven Builders, Inc.</span>
            <span class="meta mt-6">600 Lincoln Ave. Unit 90965</span>
            <span class="meta mt-6">Pasadena, CA 91109</span>
            <span class="meta mt-6">State License # 761971</span>
            <a class="meta veiled-link mt-6" href="tel:626.798.9880">Tel: 626.798.9880</a>
            <a class="meta veiled-link mt-6" href="mailto:info@newhavenbuilders.com">info@newhavenbuilders.com</a>
          </div>

        </div>
      </div>
    </section>

    <working-together-cta />

  </Layout>
</template>

<script>
import Intro from '~/components/Intro.vue'
import WorkingTogetherCta from '~/components/WorkingTogetherCta.vue'

export default {
  metaInfo: {
    title: 'Contact'
  },

  components: {
    Intro,
    WorkingTogetherCta,
  },

  data() {
    return {
      formData: {},
    }
  },

  methods: {

    encode(data) {
      return Object.keys(data)
        .map(key => encodeURIComponent(key) + '=' + encodeURIComponent(data[key]))
        .join('&')
    },

    handleSubmit(event) {
      fetch('/', {
        method: 'POST',
        headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
        body: this.encode({
          'form-name': event.target.getAttribute('name'),
          ...this.formData,
        }),
      })
      .then(() => this.$router.push('/success'))
      .catch(error => alert(error))
    },

    // If input has content add an active class to the parrent div
    inputHasContent() {
      const focusWithinElement = document.querySelectorAll('.js--hold-focus');

      focusWithinElement.forEach(element => {
        const input = element.querySelector('.js--input-watch');
        let isActive = false;

        input.addEventListener('change', () => {

          if ( input.value.length == 0 && isActive === true ) {
            element.classList.remove('has-content')
            isActive = false
          } else {
            element.classList.add('has-content')
            isActive = true
          }

        }) 
      });
    },

  },
    
  mounted() {
    this.inputHasContent()
  },
}
</script>
