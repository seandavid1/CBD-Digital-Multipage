
<template>
  <div>
    <navigation/>

    <!-- MAIN CONTAINER -->
    <b-container
      id="nav-scroller"
      ref="content"
      fluid>
      <a name="top" />
      <div class="top-area-container">
        <b-row id="homepage-top-row">
          <b-col class="homepage-top-col-1">
            <h1
              id="home"
              class="title">We'll Help You Grow Your CBD/Cannabis Business</h1>
            <p class="subtitle">Business-to-business really means people-to-people. You are in the business of selling your goods and services within the CBD and cannabis industry. You are building relationships with people running their companies&mdash;and as the local legal cannabis industry matures&mdash;CBD Digital can help you build lasting relationships and grow your businesses.</p>

            <transition name="fade">
              <b-button
                v-if="showUserGuide == false"
                class="primary-action-button-home"
                size="lg"
                variant="primary"
                @click="showUserGuide1 = true, showUserGuide = true">How can we help you?
              </b-button>
          </transition></b-col>
        </b-row>
        <!-- User Guide -->

        <!-- User Guide Row 1 -->
        <transition name="fade">
          <b-row
            v-if="showUserGuide1"
            id="user-guide"
            class="user-guide-row row-1">
            <!-- User Guide, Column 1 -->
            <b-col>
              <b-button
                size="lg"
                class="user-guide"
                @click="getButtonTwoText('cultiv')"><div class="btn-text"><span>I am a cannabis cultivator/grower.</span></div><div class="btn-image"/>
              </b-button>
            </b-col>
            <!-- User Guide, Column 2 -->
            <b-col>
              <b-button
                size="lg"
                class="user-guide"
                @click="getButtonTwoText('man')"><div class="btn-text"><span>I am a cannabis-infused products manufacturer.</span></div><div class="btn-image"/>
              </b-button>
            </b-col>
            <!-- User Guide, Column 3 -->
            <b-col>
              <b-button
                size="lg"
                class="user-guide"
                variant=""
                @click="getButtonTwoText('equip')"><div class="btn-text"><span>I am a cannabis equipment or service provider.</span></div><div class="btn-image"/>
              </b-button>
            </b-col>
          </b-row>
        </transition>

        <!-- User Guide Row 2 -->
        <transition name="fade">
          <b-row
            v-if="showUserGuide2"
            id="user-guide"
            class="user-guide-row row-2">
            <!-- User Guide, Column 1 -->
            <b-col>
              <a>
                <b-button
                  size="lg"
                  class="user-guide"
                  variant=""
                  @click="updateUserChoiceTwo('logo')">
                  <div class="btn-text"><span>I need help with<br> a new logo/mission statement.</span></div><div class="btn-image"/>
                </b-button>
              </a>
            </b-col>
            <!-- User Guide, Column 2 -->
            <b-col>
              <a>
                <b-button
                  size="lg"
                  class="user-guide"
                  variant=""
                  @click="updateUserChoiceTwo(buttonTwoTextShort)"><div
                    class="btn-text" ><span>{{ buttonTwoText }}</span> </div>
                  <div class="btn-image"/>
              </b-button></a>
            </b-col>
            <!-- User Guide, Column 3 -->
            <b-col>
              <a>
                <b-button
                  size="lg"
                  class="user-guide"
                  variant=""
                  @click="updateUserChoiceTwo('web')"><div class="btn-text"><span>I need help with<br>website design and maintenance.</span></div><div class="btn-image"/>
                </b-button>
              </a>
            </b-col>
          </b-row>
        </transition>
      </div><!-- END TOP ROW CONTAINER -->
      <!-- END USER GUIDE -->

      <!-- NESTED CONTAINER 1 -->
      <b-container
        fluid
        class="home-nested-container-1">

        <!-- ABOUT US ROW -->

        <b-row id="who-we-are">
          <b-col>
            <h2>Who We Are</h2>
          </b-col>
        </b-row>
        <b-row>
          <b-col
            lg="6"
            md="12"
            sm="12"><img
              class="about-cbd-img"
              alt="about-cbd-digital"
              src="~/assets/images/cbd-about-us.jpg" >
          </b-col>
          <b-col
            lg="6"
            md="12"
            sm="12"><p class="about-text">With experience in the cannabis market, Boston-based CBD Digital brings 20+ years of B2B marketing strategy to the table—including brand development, inbound marketing, graphic and website design, web development, content creation, and social media management. We partner with you to achieve new opportunities and sustained success in the cannabis industry and are committed to your business goal: <strong>growth!</strong></p>
        </b-col></b-row>

        <!-- Marketing ROW-->
        <b-row id="marketing">
          <b-col>
            <h2 class="center">Your B2B Cannabis Marketing Resource</h2>
            <p class="center">As a marketing resource for the legal New England cannabis industry, we can help you grow your business. You’re busy focusing on either cultivation, equipment, supplies, or retailers—we know your time and expertise for B2B marketing is limited.</p>

            <p class="center"><strong>You may not know where to begin with a marketing plan or basic strategies. But we do.</strong> </p>
          </b-col>
        </b-row>


        <!-- SERVICES ROW-->
        <b-row
          id="services"
          class="section">
          <b-col>
            <h2 class="center">Services We Provide</h2>
            <p class="center">As a full-service marketing agency, we can guide you through the many elements that a solid business-to-business marketing strategy requires. Click on the services below to see how we can help you.</p>
          </b-col>
        </b-row>
        <!-- Services Row 1 -->
        <b-row>
          <!--COL 1 -->
          <b-col
            sm="12"
            md="6"
            lg="4">
            <div class="services-block">
                <nuxt-link :to="'/branding?segment=' + urlSegmentOne + '&help=' + urlSegmentTwo" >
              <h2 brandingModal>Branding</h2>
                </nuxt-link>
            </div>
          </b-col>
          <!-- COL 2 -->
          <b-col
            sm="12"
            md="6"
            lg="4">
            <div class="services-block">
              <nuxt-link :to="'/Marketing?segment=' + urlSegmentOne + '&help=' + urlSegmentTwo">
                <h2>Marketing</h2>
              </nuxt-link>
            </div>
          </b-col>
          <!-- COL 3 -->
          <b-col
            sm="12"
            md="6"
            lg="4">
            <div class="services-block">
              <nuxt-link :to="'/graphic-design?segment=' + urlSegmentOne + '&help=' + urlSegmentTwo" >
                <h2>Graphic<br>Design</h2>
              </nuxt-link>
            </div>
          </b-col>
          <!-- ROW 2 -->
          <!-- COL 1 -->
          <b-col
            sm="12"
            md="6"
            lg="4">
            <div class="services-block">
              <nuxt-link :to="'/web-design-and-development?segment=' + urlSegmentOne + '&help=' + urlSegmentTwo">
                <h2>Web<br>Development</h2>
              </nuxt-link>
            </div>
          </b-col>
          <!-- Col 2 -->
          <b-col
            sm="12"
            md="6"
            lg="4">
            <div class="services-block">
              <nuxt-link :to="'/content-creation?segment=' + urlSegmentOne + '&help=' + urlSegmentTwo" >
                <h2 v-b-modal.contentModal>Content<br>Creation</h2>
              </nuxt-link>
            </div>
          </b-col>
          <!-- Col 3 -->
          <b-col
            sm="12"
            md="6"
            lg="4">
            <div class="services-block">
              <nuxt-link :to="'/social-media?segment=' + urlSegmentOne + '&help=' + urlSegmentTwo" >
                <h2 v-b-modal.socialModal>Social<br>Media</h2>
              </nuxt-link>
            </div>
          </b-col>
        </b-row>
        <b-row
          id="tech"
          class="section">
          <b-col>
            <h2 class="center">Technology We Love</h2>
            <p class="center">Admittedly, we’re a little tech nerdy, which is great news for our clients. Staying on top of development trends, marketing research, and cutting-edge web applications allows us keep you a step ahead of the competition. Here are some of the technology platforms we use to provide the latest marketing strategies for you.</p>
          </b-col>
        </b-row>
        <b-row>
          <b-col
            sm="12"
            md="4"
            lg="3"
            xl="2"><div
              v-b-popover.hover="'HubSpot is our CRM of choice. Its powerful lead management tools give you an edge on the competition.'"
              title="HubSpot CRM"
              class="hubspot-logo logo"><div>&nbsp;</div></div></b-col>
          <b-col
            sm="12"
            md="4"
            lg="3"
            xl="2"><div
              v-b-popover.hover="'WordPress is the world\'s most popular open-source CMS. It\'s a robust, fully customizable content management solution that allows for editing of your website copy with minimal learning curve.'"
              title="WordPress CMS"
              class="wordpress-logo logo"><div>&nbsp;</div></div></b-col>
          <b-col
            sm="12"
            md="4"
            lg="3"
            xl="2"><div
              v-b-popover.hover="'WooCommerce is the leading e-commerce solution for Wordpress. Its scalability makes it a great fit for businesses small and large that want to begin selling products and services online. And best of all, it\'s open source.' "
              title="WooCommerce"
              class="woocommerce-logo logo"><div>&nbsp;</div></div></b-col>
          <b-col
            sm="12"
            md="4"
            lg="3"
            xl="2"><div
              v-b-popover.hover="'A2 Hosting offers fast, reliable shared and dedicated hosting, plus must-have add-ons like dedicated IPs and SSL certificates, all at competitive prices.' "
              title="A2 Hosting"
              class="a2-logo logo"><div>&nbsp;</div></div></b-col>
          <b-col
            sm="12"
            md="4"
            lg="3"
            xl="2"><div
              v-b-popover.hover="'PHP is the open-source, server-side scripting language which powers the WordPress sites we build, and MySQL is the database software it communicates with. These are the stable and reliable choices for backend web technologies we lean on most heavily for client web development.' "
              title="PHP/MySQL"
              class="php-logo logo"><div>&nbsp;</div></div></b-col>
          <b-col
            sm="12"
            md="4"
            lg="3"
            xl="2"><div
              v-b-popover.hover="'Vue.js is the javascript framework this website is built on. It\'s open-source, reactive, component-driven, and extremely fast on the front end.' "
              title="Bootstrap"
              class="vue-logo logo"><div>&nbsp;</div></div></b-col>
          <b-col
            sm="12"
            md="4"
            lg="3"
            xl="2"><div
              v-b-popover.hover="'Bootstrap is an open-source toolkit for quickly prototyping or building out HTML, CSS and JS. It speeds up development time, has a great grid and component system, and is mobile-first.' "
              title="Bootstrap"
              class="bootstrap-logo logo"><div>&nbsp;</div></div></b-col>
          <b-col
            sm="12"
            md="4"
            lg="3"
            xl="2"><div
              v-b-popover.hover="'Google Analytics is the industry standard for web performance metrics. Coupled with a great CRM like HubSpot, our team can use this tool to provide you enormous insight on the performance of your site.' "
              title="Google Analytics"
              class="google-logo logo"><div>&nbsp;</div></div></b-col>
          <b-col
            sm="12"
            md="4"
            lg="3"
            xl="2"><div
              v-b-popover.hover="'SurveyMonkey is a great, free resource for sending out surveys, polls, and general emails to your users, helping you keep a finger on the pulse of your customer base.' "
              title="SurveyMonkey"
              class="survey-logo logo"><div>&nbsp;</div></div></b-col>
          <b-col
            sm="12"
            md="4"
            lg="3"
            xl="2"><div
              v-b-popover.hover="'Our creative department boasts many decades of expertise in Photoshop, Illustrator, InDesign and the entire Adobe Creative Suite.' "
              title="Adobe Creative Cloud"
              class="adobe-logo logo"><div>&nbsp;</div></div></b-col>
          <b-col
            sm="12"
            md="4"
            lg="3"
            xl="2"><div
              v-b-popover.hover="'We use Slack as our primary mode of inter-office communication, keeping our workday humming so we can serve our clients at hyperspeed.' "
              title="Slack"
              class="slack-logo logo"><div>&nbsp;</div></div></b-col>
          <b-col
            sm="12"
            md="4"
            lg="3"
            xl="2"><div
              v-b-popover.hover="'Moz is a powerhouse tool for SEO, allowing for deep, granular audits of site performance, helping us identify and correct web issues before they hurt you in the rankings.' "
              title="Moz"
              class="moz-logo logo"><div>&nbsp;</div></div></b-col>
        </b-row>

        <b-row
          id="contact"
          class="section">
          <b-col>
            <h2 class="center">Contact Us</h2>
            <p
              class="center"
              v-html="contactUsCopy"/>
            <p
              class="center additional"
              v-html="additionalContactCopy" />
            <BottomForm/>
          </b-col>
        </b-row>
      </b-container>
    </b-container>
    <div class="fade-box">&nbsp;
    </div>

    <script type="text/javascript">

      // JQUERY FORM MANIPULATION
      $( document ).ready(function() {
      console.log( 'ready!' );
      var h = Math.max(document.documentElement.clientHeight, window.innerHeight || 0);
      var height = (h-100);
      $('#nav-scroller').css('height',height);
      console.log(h);
      window.addEventListener('resize', resizeFunction);
      function resizeFunction() {
      console.log('resize');
      var h2 = Math.max(document.documentElement.clientHeight, window.innerHeight || 0);
      var height2 = (h2-100);
      $('#nav-scroller').css('height',height2);
      };
      });

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
      target: '#cbd-hubspot-form',
      onFormReady($form, ctx){
      console.log( 'ready!' );
      $('#cbd-hubspot-form input#firstname-1f389b80-f287-4169-a11a-52dd42528728').addClass('found-you');
      $('#cbd-hubspot-form select').val('{{ choiceOne }}').change();
      }
      });
    </script>

    <!-- Start of HubSpot Embed Code -->
    <script
      id="hs-script-loader"
      type="text/javascript"
      async
      defer
      src="//js.hs-scripts.com/381132.js"/>
      <!-- End of HubSpot Embed Code -->
  </div>


  <!-- END SCROLLPSPY TEST -->
</template>

<script>
import Logo from '~/components/Logo.vue'
import Carousel from '~/components/Carousel.vue'
import Navigation from '~/components/Navigation.vue'
import BottomForm from '~/components/BottomForm.vue'

export default {
  components: {
    Logo,
    Carousel,
    Navigation,
    BottomForm
  },
  data: function() {
    return {
      showUserGuide: false,
      showUserGuide1: false,
      showUserGuide2: false,
      cultivator: false,
      manufacturer: false,
      equipment: false,
      buttonTwoText: '',
      buttonTwoTextShort: '',
      cultivatorBtnTxt:
        'I need help with content/messaging to reach retailers and value-added resellers.',
        cultivatorBtnTxtShort: 'var',
      manufacturerBtnTxt:
        'I need help with content/messaging to reach retailers and dispensaries.',
        manufacturerBtnTxtShort: 'disp',
      equipmentBtnTxt:
        'I need help with content/messaging to reach growers and retailers.',
        equipmentBtnTxtShort: 'grow',
      contactUsCopy:
        'We’re as excited about the advances being made in New England’s legal cannabis industry as you are! Experts in B2B marketing, we’re here to help you connect with the people behind the companies that are looking for your products and services. Contact us now&mdash;<strong>let’s grow your business!</strong>',
      additionalContactCopy:
        "Send us your contact info and we'll get started on a marketing plan just for you.",
      targetURL: ''
    }
  },
  computed: {
    urlSegmentOne() {
      return this.$store.state.choiceOne
    },
    urlSegmentTwo() {
      return this.$store.state.choiceTwo
    },
    choiceOne() {
      const choice = this.$store.state.choiceOne
      if (choice === 'nothing') {
        return choice
      } else if (choice === 'cultiv') {
        return 'I am a cannabis cultivator/grower.'
      } else if (choice === 'man') {
        return 'I am a cannabis-infused products manufacturer.'
      } else if (choice === 'equip') {
        return 'I am a cannabis equipment<br> or service provider.'
      }
    },
    choiceTwo() {
      const choice = this.$store.state.choiceTwo
      if (choice === 'nothing') {
        return choice
      } else if (choice === 'logo') {
        return 'I need help with a new logo/mission statement.'
      } else if (choice === 'web') {
        return 'I need help with website design and maintenance.'
      } else {
        return choice
      }
    }
  },
  methods: {
    scrollIntoView(evt) {
      evt.preventDefault()
      const href = evt.target.getAttribute('href')
      const el = href ? document.querySelector(href) : null
      if (el) {
        this.$refs.content.scrollTop = el.offsetTop
      }
    },
    getButtonTwoText: function(choice) {
      if (choice === 'cultiv') {
        this.cultivator = true
        this.buttonTwoText = this.cultivatorBtnTxt
        this.buttonTwoTextShort = this.cultivatorBtnTxtShort
        this.showUserGuide1 = false
        this.showUserGuide2 = true
      }
      if (choice === 'man') {
        this.manufacturer = true
        this.buttonTwoText = this.manufacturerBtnTxt
        this.buttonTwoTextShort = this.manufacturerBtnTxtShort
        this.showUserGuide1 = false
        this.showUserGuide2 = true
      }
      if (choice === 'equip') {
        this.equipment = true
        this.buttonTwoText = this.equipmentBtnTxt
        this.buttonTwoTextShort = this.equipmentBtnTxtShort
        this.showUserGuide1 = false
        this.showUserGuide2 = true
      }
      this.updateUserChoice(choice)
    },
    updateUserChoice(choice) {
      this.$store.commit('updateUserChoiceOne', choice)
      var betterChoice = this.choiceOne.replace('I am', 'You are')
      this.contactUsCopy =
        'Thanks for telling us more about you! <br> <span class="about-you-contact"><strong>About You:</strong> ' +
        betterChoice +
        '</span>'
      console.log(this.choiceOne)
      $('#cbd-hubspot-form select')
        .val(this.choiceOne)
        .change()
      $('.hs_to_what_segment_of_the_cannabis_market_do_you_belong_').css(
        'display',
        'none'
      )
    },
    updateUserChoiceTwo(choice) {
      this.$store.commit('updateUserChoiceTwo', choice)
      console.log(choice)
      var betterChoiceOne = this.choiceOne.replace('I am', 'You are')
      var betterChoiceTwo = this.choiceTwo.replace('I', ' You')
      this.showUserGuide2 = false
      if (choice === 'logo') {
        this.targetURL = '/branding?segment='
      }
      if (choice === 'var' || choice === 'disp' || choice === 'grow') {
        this.targetURL = '/marketing?segment='
      }
      if (choice === 'web') {
        this.targetURL = '/web-design-and-development?segment='
      } 
      this.targetURL += this.urlSegmentOne + '&help=' + this.urlSegmentTwo
      $(
        '#cbd-hubspot-form select#what_can_we_help_you_with_-4019399f-6e52-42ab-882b-27ccf9cf750d'
      )
        .val(this.choiceTwo)
        .change()
      $('.hs_what_can_we_help_you_with_').css('display', 'none')
      this.contactUsCopy =
        'Thanks for telling us more about you! <br> <span class="about-you-contact"><strong>About You:</strong> ' +
        betterChoiceOne +
        ' ' +
        betterChoiceTwo +
        '</span>'
        this.$router.push({
          path: this.targetURL
        })
    },
    head() {
    return {
      title: 'CBD Digital Group',
      meta: [
        {hid:  'description', name: 'description', content: 'description' }
      ]
    }
  },
    counter() {
      this.$store.commit('increment')
    }
  },
  layout: 'homepage'
}
</script>


<style scoped>
.title {
  display: block;
  font-size: 54px;
  color: #fff;
  letter-spacing: 1px;
  max-width: 900px;
  line-height: 65px;
}
.subtitle {
  max-width: 83%;
  text-align: left;
  font-size: 25px;
  color: #fff;
  margin-left: 6%;
  margin-top: 35px;
  line-height: 34px;
  font-weight: 500;
  letter-spacing: -0.14px;
}
.links {
  padding-top: 15px;
}
#homepage .carousel {
  margin-bottom: 40px;
}
#homepage article.card {
  margin: 0 auto;
}
#homepage-top-area {
  padding-bottom: 60px;
  height: 420px;
}
.top-area-container {
  background-image: url('~assets/images/cbd-digital-home-banner-bg-small.jpg');
  background-repeat: no-repeat;
  background-size: 100%;
  height: 580px;
}
div#homepage-top-row {
  padding-top: 70px;
}
.homepage-top-col-1 {
  text-align: center;
  padding-bottom: 0px;
  height: 325px;
}
.homepage-top-col-2 {
  text-align: center;
  height: 300px;
}
h1#home {
  text-align: left;
  margin-left: 6%;
}
#user-guide {
  text-align: center;
}
.user-guide-row {
  margin-top: 25px;
}
.fade-enter-active {
  transition: opacity 1.5s;
}
.fade-leave-active {
  transition: opacity 0s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
.slide-fade-enter-active {
  transform: translateY(10px);
  transition: all 2.5s ease;
}
.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
#services {
  margin-top: 30px;
}
button.btn.primary-action-button-home.btn-primary.btn-lg {
  border: 10px solid #fff;
  font-size: 35px;
  border-width: 2px;
  padding: 2px 115px;
  border-radius: 10px;
  font-weight: 500;
  text-transform: capitalize;
  margin-top: 50px;
}
#nav-scroller {
  position: relative;
  height: 600px;
  overflow-y: scroll;
  padding: 0px;
}
.fade-box {
  height: 24px;
  margin-top: -24px;
  background: linear-gradient(
    to bottom,
    rgba(255, 255, 255, 0) 0%,
    rgba(255, 255, 255, 1) 100%
  );
  filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#ffffff', endColorstr='#ffffff',GradientType=0 );
  position: absolute;
  width: 100%;
  z-index: 999999;
}
.about-image-placeholder.col {
  background: #616e75;
  padding-bottom: 40px;
  min-height: 492px;
  background: rgb(84, 84, 84);
  background: linear-gradient(
    135deg,
    rgba(84, 84, 84, 1) 25%,
    rgba(188, 188, 188, 1) 50%,
    rgba(84, 84, 84, 1) 77%
  );
  filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#545454', endColorstr='#545454',GradientType=1 );
}
.home-nested-container-1.container-fluid {
  padding: 0px 9%;
}
p.about-text {
  margin-left: 0px;
}
p {
  font-size: 28px;
}
img.about-cbd-img {
  max-width: 100%;
  margin-bottom: 20px;
}
#services p {
  max-width: 800px;
  margin: 0 auto 30px;
}
.logo {
  border: 3px solid #aaa;
  margin: 0 auto 20px;
  height: 118px;
  width: 170px;
}
.logo > div {
  height: 112px;
  width: 166px;
  transition-duration: 0.7s;
  background-repeat: no-repeat;
  opacity: 1;
}
.logo > div:hover {
  transition-duration: 0.5s;
  cursor: pointer;
  opacity: 0.6;
}
.hubspot-logo {
  border-color: #f37521;
}
.hubspot-logo > div:hover {
  background-image: url('../assets/images/hubspot-logo-gray.jpg');
}
.hubspot-logo > div {
  background-image: url('../assets/images/hubspot-logo-color.jpg');
}
.wordpress-logo {
  border-color: #20759b;
}
.wordpress-logo > div:hover {
  background-image: url('../assets/images/wordpress-logo-gray.png');
}
.wordpress-logo > div {
  background-image: url('../assets/images/wordpress-logo-color.jpg');
}
.woocommerce-logo {
  border-color: #9e5b90;
}
.woocommerce-logo > div:hover {
  background-image: url('../assets/images/woocommerce-logo-gray.jpg');
}
.woocommerce-logo > div {
  background-image: url('../assets/images/woocommerce-logo-color.jpg');
}
.a2-logo {
  border-color: #669940;
}
.a2-logo > div:hover {
  background-image: url('../assets/images/a2-hosting-logo-gray.jpg');
}
.a2-logo > div {
  background-image: url('../assets/images/a2-hosting-logo-color.jpg');
}
.php-logo {
  border-color: #6a7db6;
}
.php-logo > div:hover {
  background-image: url('../assets/images/php-logo-gray.jpg');
}
.php-logo > div {
  background-image: url('../assets/images/php-logo-color.jpg');
}
.vue-logo {
  border-color: #4cb986;
}
.vue-logo > div:hover {
  background-image: url('../assets/images/vue-logo-gray.jpg');
}
.vue-logo > div {
  background-image: url('../assets/images/vue-logo-color.jpg');
}
.bootstrap-logo {
  border-color: #563c7e;
}
.bootstrap-logo > div:hover {
  background-image: url('../assets/images/bootstrap-logo-gray.jpg');
}
.bootstrap-logo > div {
  background-image: url('../assets/images/bootstrap-logo-color.jpg');
}
.google-logo {
  border-color: #f37e20;
}
.google-logo > div:hover {
  background-image: url('../assets/images/google-analytics-logo-gray.jpg');
}
.google-logo > div {
  background-image: url('../assets/images/google-analytics-logo-color.jpg');
}
.survey-logo {
  border-color: #2db56e;
}
.survey-logo > div:hover {
  background-image: url('../assets/images/survey-monkey-logo-gray.jpg');
}
.survey-logo > div {
  background-image: url('../assets/images/survey-monkey-logo-color.jpg');
}
.adobe-logo {
  border-color: #d11f26;
}
.adobe-logo > div:hover {
  background-image: url('../assets/images/adobe-logo-color-gray.jpg');
}
.adobe-logo > div {
  background-image: url('../assets/images/adobe-logo-color.jpg');
}
.slack-logo {
  border-color: #85cee5;
}
.slack-logo > div:hover {
  background-image: url('../assets/images/slack-logo-gray.jpg');
}
.slack-logo > div {
  background-image: url('../assets/images/slack-logo-color.jpg');
}
.moz-logo {
  border-color: #2193d1;
}
.moz-logo > div:hover {
  background-image: url('../assets/images/moz-logo-gray.jpg');
}
.moz-logo > div {
  background-image: url('../assets/images/moz-logo-color.jpg');
}
.modal-services p {
  font-size: 19px;
}
.modal-content {
  max-height: 620px;
}
div#cbd-hubspot-form {
  background: #ddd;
  max-width: 100%;
}
.services-block {
  width: 100%;
  height: 240px;
  background-repeat: no-repeat;
  background-size: auto 100%;
  background-image: url('../assets/images/cbd-services-bg.png');
  cursor: pointer;
  margin-bottom: 30px;
}
.services-block:hover {
  background-image: url('../assets/images/cbd-services-bg-active.png');
}
.services-block h2 {
  color: #fff;
  margin-top: 0px;
  height: 240px;
  vertical-align: middle;
  text-align: center;
  display: table-cell;
  width: 400px;
  font-size: 40px;
  text-transform: uppercase;
  font-weight: 700;
}
.services-block a:hover {
  text-decoration: none;
}

p.start-over {
  margin-top: -38px;
  text-align: right;
  max-width: 95%;
  font-size: 14px;
  font-weight: 700;
  text-transform: uppercase;
}
/* Fix weird double form issue */

div#cbd-hubspot-form iframe:nth-child(2) {
    display: none !important;
}


/* RESPONSIVE */
@media (max-width: 1100px) {
  .top-area-container {
    background-size: auto 100%;
    height: 580px;
  }
  .services-block h2 {
    font-size: 34px;
  }
}
@media (max-width: 992px) {
  div#homepage-top-row {
    padding-top: 45px;
  }
  .navbar-nav {
    margin-left: 0%;
  }
  .home-link {
    display: none;
  }
  .top-area-container {
    background-size: auto 100%;
    height: 630px;
  }
  .homepage-top-col-1 {
    height: auto;
  }
  h1#home {
    text-align: center;
    margin-left: 0px;
    font-size: 57px;
    line-height: 57px;
  }
  .subtitle {
    max-width: 100%;
    text-align: center;
    margin-left: auto;
    margin-right: auto;
    margin-top: 15px;
    font-size: 22px;
    line-height: 28px;
  }
  button.btn.primary-action-button-home.btn-primary.btn-lg {
    margin-top: 10px;
  }
  #user-guide .col,
  .user-guide-row.row-2 .col {
    flex-basis: 100%;
  }
  .user-guide-row {
    margin-top: 15px;
  }
  button.btn.user-guide.btn-lg {
    height: 80px;
    width: 80%;
    margin-bottom: 10px;
  }
  button.btn.user-guide.btn-lg > div.btn-text > span {
    height: 80px;
    width: 30%;
  }
  button.btn.user-guide.btn-lg > div.btn-image {
    width: 15%;
    background-size: 50%;
  }
  button.btn.user-guide.btn-lg > div.btn-text {
    width: 85%;
  }
}

@media (max-width: 800px) {
  .nav-link {
    font-size: 15px;
  }
}

@media (max-width: 767px) {
  button.btn.primary-action-button-home.btn-primary.btn-lg {
    margin-left: 0%;
    padding: 5px 40px;
  }
  .nav-link {
    font-size: 20px;
    max-width: 200px;
  }
  .user-guide-row button {
    height: 70px;
    margin-bottom: 10px;
    margin-top: 7px;
  }
  div#homepage-top-row {
    padding-top: 40px;
  }
  .homepage-top-col-1 {
    height: auto;
  }
  h1#home {
    font-size: 47px;
    line-height: 50px;
  }
  .subtitle {
    font-size: 20px;
    line-height: 26px;
  }
  .top-area-container {
    height: 710px;
  }
  button.btn.user-guide.btn-lg {
    width: 100%;
  }
  .img-right {
    float: none;
    margin: 0px auto 20px;
    width: 100%;
  }
  .fade-box {
    display: none;
  }
}

@media (max-width: 576px) {
  p {
    font-size: 24px;
  }
  p.about-text {
    margin-left: 0px;
    margin-top: 30px;
  }
  article.card.mb-2 {
    margin: 30px auto;
  }
  h1#home {
    font-size: 42px;
    line-height: 46px;
  }
  .subtitle {
    font-size: 17px;
  }
  .top-area-container {
    height: 780px;
  }
  .user-guide-row button[data-v-2a183b29] {
    height: auto;
    font-size: 16px;
  }
  button.btn.user-guide.btn-lg > div.btn-text > span {
    line-height: 22px;
  }
  button.btn.primary-action-button-home.btn-primary.btn-lg {
    padding: 5px 30px;
    font-size: 28px;
  }
  p.start-over {
    margin-top: 0px;
    max-width: 100%;
    text-align: right;
    font-size: 16px;
  }
}

@media (max-width: 400px) {
  button.btn.user-guide.btn-lg > div.btn-image {
    width: 10%;
    background-size: 70%;
  }
  button.btn.user-guide.btn-lg > div.btn-text {
    width: 90%;
  }
  button.btn.primary-action-button-home.btn-primary.btn-lg {
    font-size: 22px;
    max-width: 100%;
  }
  button.btn.user-guide.btn-lg > div.btn-text > span {
    line-height: 17px;
  }
  button.btn.user-guide.btn-lg {
    font-size: 17px;
  }
}
</style>
