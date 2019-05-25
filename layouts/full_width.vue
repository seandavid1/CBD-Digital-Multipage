<template>
  <div>
      <navigation/>
    <b-container class="default">
      <b-row>
          <h1>{{title}}
          </h1>
          <!-- FIX THE PAGE NAME REFRESH WITH URL PARAMS?
                  OR MOVE ALL THIS CODE INTO THE PAGE 

                  OR MAYBE THE ROUTER REMEMBERS THE NAME BUT NOT THE PATH?
                  TRY FIRST
          -->
          <p></p>
      </b-row>
      <b-row class="social-share-full-page-width">
        <SocialShareBar :url="url" :title="title" hashtags="cbdDigital" />
      </b-row>
      <b-row>
        <b-col
          xl="12"
          lg="12"
          md="12"
          sm="12">
          <div>
            <div class="wordpress-content">
                <nuxt/>
            </div>
        </div></b-col>
      </b-row>
      <b-row>
        <transition name="fade">
          <div class="bottom-form-container">
          <BottomForm/>
          </div>
        </transition>
      </b-row>
    </b-container>

    <!-- Global site tag (gtag.js) - Google Analytics -->
    <script
      async
      src="https://www.googletagmanager.com/gtag/js?id=UA-133563244-1"/>
    <script>
      window.dataLayer = window.dataLayer || [];
      function gtag(){dataLayer.push(arguments);}
      gtag('js', new Date());

      gtag('config', 'UA-133563244-1');
    </script>

    <!-- HubSpot Form / Talks to SideForm/BottomForm Components -->
    <script
      charset="utf-8"
      type="text/javascript"
      src="//js.hsforms.net/forms/shell.js"/>
    <script charset="utf-8">
      hbspt.forms.create({
      portalId: '5208608',
      formId: '1f389b80-f287-4169-a11a-52dd42528728',
      target: '#cbd-hubspot-form'
      });
    </script>

    <!-- Start of HubSpot Embed Code -->
<script type="text/javascript" id="hs-script-loader" async defer src="//js.hs-scripts.com/5208608.js"></script>
<!-- End of HubSpot Embed Code -->
  </div>

</template>

<script>
import BottomForm from '~/components/BottomForm.vue'
import SocialShareBar from '~/components/SocialShareBar.vue'
import Navigation from '~/components/Navigation.vue'
import Logo from '~/components/Logo.vue'
export default {
   components: {
    BottomForm,
    SocialShareBar,
    Navigation
  },
  data() {
    return {
      errors: [],
      pageTitle: ''
    }
  },
  computed: {
    url() {
      var baseURL = this.$store.state.baseURL
      var path = this.$nuxt.$route.path
      var url = baseURL + path
      return url
    },
    title () {
      return this.$route.matched.map((r) => {
        return (r.components.default.options ? r.components.default.options.pageTitle : r.components.default.pageTitle)
      })[0]
    }
  },
  created() {
    this.$store.dispatch('getPages')
  },
}
</script>
