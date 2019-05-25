
<template>
  <div>
    <!-- SCROLLSPY NAV -->
    <b-navbar
      toggleable="md"
      type="light"
      variant="primary-inverse"
      fixed="top">

      <b-navbar-toggle target="nav_collapse"/>

      <b-navbar-brand
        @click="scrollIntoView"><logo/></b-navbar-brand>

      <b-collapse
        id="nav_collapse"
        is-nav>

        <b-navbar-nav
          v-b-scrollspy:nav-scroller
          pills>
          <b-nav-item
            href="#homepage-top-row"
            class="home-link"
            @click="scrollIntoView">Home</b-nav-item>
          <b-nav-item
            href="#who-we-are"
            @click="scrollIntoView">Who We Are</b-nav-item>
          <b-nav-item
            href="#services"
            @click="scrollIntoView">Services</b-nav-item>
          <b-nav-item
            href="#tech"
            @click="scrollIntoView">Technology</b-nav-item>
          <b-nav-item
            href="#contact"
            @click="scrollIntoView">Contact Us</b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>

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
                title="Popover Title"
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
                @click="getButtonTwoText('cult')"><div class="btn-text"><span>I am a cannabis cultivator/grower.</span></div><div class="btn-image"/>
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
              <a href="#contact">
                <b-button
                  size="lg"
                  class="user-guide"
                  variant=""
                  @click="updateUserChoiceTwo('logo')"><div class="btn-text"><span>I need help with<br> a new logo/mission statement.</span></div><div class="btn-image"/>
                </b-button>
              </a>
            </b-col>
            <!-- User Guide, Column 2 -->
            <b-col>
              <a href="#contact">
                <b-button
                  size="lg"
                  class="user-guide"
                  variant=""
                  @click="updateUserChoiceTwo(buttonTwoText)"><div
                    class="btn-text" ><span>{{ buttonTwoText }}</span> </div>
                  <div class="btn-image"/>
              </b-button></a>
            </b-col>
            <!-- User Guide, Column 3 -->
            <b-col>
              <a href="#contact">
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
              src="~assets/images/cbd-about-us.jpg" >
          </b-col>
          <b-col
            lg="6"
            md="12"
            sm="12"><p class="about-text">With expertise in the cannabis market, Boston-based CBD Digital brings 20+ years of B2B marketing strategy to the table—including brand development, inbound marketing, graphic and website design, web development, content creation, and social media management. We partner with you to achieve new opportunities and sustained success in the cannabis industry and are committed to your business goal: <strong>growth!</strong></p>
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
            <p class="center">As a full-service marketing agency, we can guide you through the many elements that a solid business-to-business marketing strategy requires. Click on the segments below to see how we can help you.</p>
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
              <h2 v-b-modal.brandingModal>Branding</h2>


              <b-modal
                id="brandingModal"
                class="modal-services"
                title="Branding">
                <div class="modal-container">
                  <p><img
                    src="~assets/images/branding-primary-image.jpg"
                    class="img-right services-img"><strong>Branding.</strong> When customers think of your company, your products, or the services you provide, they should “emotionally” associate with them in a way that aligns with their values, beliefs, and business goals. To do this, your business needs to know “who” and “why” it is in business—and have the capability to communicate that in a way that translates real shared meaning with your prospects and customers. We can guide you through a comprehensive brand development process, which will help you uncover your who and why so we can create branding—messaging, logos, color schemes, etc.—that distinguish you from other businesses in the cannabis space. </p>

                  <p><strong>Rebranding.</strong> Interested in breaking into a new market—the legal local cannabis market, perhaps? Rebranding should be step one on your journey. It doesn’t need to be a full, company-wide rebrand, and might focus solely on one division. It’s possible to pivot your business model and messaging to attract cannabis-related businesses to you. Rebranding helps you put a new voice and look to your rediscovered purpose, re-aligning your purpose so your prospects and customers know clearly who you are.</p>

                  <p><strong>CBD Digital Delivers:</strong></p>

                  <p><ul><li>Brand development process: discovery sessions, interviews, executive summary</li>
                    <li>Strong brand identity: logos, positioning statement, corporate messaging</li>
                  <li>Color palette</li></ul></p>
                </div>

              </b-modal>
            </div>
          </b-col>
          <!-- COL 2 -->
          <b-col
            sm="12"
            md="6"
            lg="4">
            <div class="services-block">
              <h2 v-b-modal.marketingModal>Marketing</h2>
              <b-modal
                id="marketingModal"
                class="modal-services"
                title="Marketing">
                <div class="modal-container">
                  <p><img
                    src="~assets/images/marketing-primary-image.jpg"
                    class="img-right services-img"><strong>Marketing.</strong> As a business trying to capture the attention of people in an oversaturated world, you need to cut through the confusion and get people the information they need that is most helpful and relevant to them. This way, they find you without you having to rely on ineffective old sales tactics. As a HubSpot partner, we use all the power that the HubSpot platform, marketing’s premier comprehensive marketing and sales platform, offers.</p>

                  <p>Hardly new, though often misunderstood, inbound marketing is the leading strategy for marketing and selling in both the B2B and B2C markets these days. Does it work? Yep. If you are reading this, inbound marketing is probably what got you here. It’s the largest, most successful component of digital marketing. It’s immensely powerful, pervasive, and persuasive—yet many people don’t even realize they benefit from it every day.</p><p/>

                  <p>It works because the search questions you put into your browser get answered directly and specifically. The beauty of it is its convenience: you can search for what you want, when you want. If a company’s website is up to date, you’re able to make timely, knowledgeable, and efficient decisions. Flip that—and imagine providing that amazing service to your cannabis customers and prospects. We can create the cannabis marketing strategies and content that will do just that.</p>

                  <p><strong>CBD Digital Delivers:</strong></p>

                  <p><ul><li>Inbound marketing plans and strategies</li>

                    <li>Email marketing</li>

                    <li>Video marketing</li>

                    <li>Landing pages</li>

                  <li>Calls to action (CTAs)</li></ul></p>
                </div>

              </b-modal>
            </div>
          </b-col>
          <!-- COL 3 -->
          <b-col
            sm="12"
            md="6"
            lg="4">
            <div class="services-block">
              <h2 v-b-modal.graphicModal>Graphic<br>Design</h2>
              <b-modal
                id="graphicModal"
                class="modal-services"
                title="Graphic Design">
                <div class="modal-container">
                  <p><img
                    src="~assets/images/graphic-design-primary-image.jpg"
                    class="img-right services-img"></p><p><strong> Graphic Design. </strong> Good graphic design communicates your brand with subtly and strength. It’s more than just a logo—it projects a feeling and identity that you and your customers and prospects instantly “get” and relate to. Design should represent your brand while also appealing to your target audience. We’re here to make that happen for you.</p>

                  <p><strong>Packaging Design.</strong> As your business matures and changes within the growing cannabis industry, you’ll be bringing new products to market, which may require new packaging. Our talented design team will create packaging that communicates your unique brand, giving you the expression and exposure that will help move product. Our connections within the B2B ecosystem affords us insight to packaging requirements and trends. </p>

                  <p><strong>CBD Digital Delivers:</strong></p>
                  <b-row>
                    <b-col>
                      <p><ul><li>Brochures </li>
                        <li>Corporate collateral: sell sheets, infographics,
                        white papers, business cards, etc.</li></ul></p></b-col>

                    <b-col>
                      <p>
                        <ul>
                          <li>Trade show booths</li>
                          <li>Print and digital ad design</li>
                      <li>Packaging design</li></ul></p>
                    </b-col>
                  </b-row>
                </div>
              </b-modal>
            </div>
          </b-col>
          <!-- ROW 2 -->
          <!-- COL 1 -->
          <b-col
            sm="12"
            md="6"
            lg="4">
            <div class="services-block">
              <h2 v-b-modal.webModal>Web<br>Development</h2>
              <b-modal
                id="webModal"
                class="modal-services"
                title="Web Development">
                <div class="modal-container">
                  <p><img
                    src="~assets/images/web-primary-image.jpg"
                    class="img-right services-img"><strong>Web Design.</strong> Your website is your company’s digital doorbell. It better be welcoming and informative so people will want to extend their visit and look around. (You only have seconds to grab their attention—or you lose them.) Your website is your most powerful marketing and sales tool, and we’ll design it with the style, intuitive flow, and functionality needed to attract the cannabis business you want. We can use your current brand identity or design a new one after re-branding your cannabis business with you and will write branded material to fill your pages with relevant, helpful, SEO-optimized content. </p>

                  <p><strong>Web Development.</strong> Good design is one element of a successful website. Think of development as the behind-the-scenes mechanism that keeps it running efficiently: SEO, analytics, automation, among other functions. With all the talk of what it takes to attract prospects and customers to your website with content, we also provide the processes and technical expertise to optimize and maintain your website’s performance with speed, function, and a positive user experience (UX).</p>

                  <p><strong>CBD Digital Delivers:</strong></p>
                  <b-row>
                    <b-col>
                      <p><ul><li>Website design and ongoing development</li>
                        <li>Web page content creation </li>
                    <li>Website performance optimization </li></ul></p></b-col>

                    <b-col>
                      <p>
                        <ul>
                          <li>Automation and analytics</li>
                          <li>Search engine optimization (SEO)</li>
                      <li>Microsites</li></ul></p>
                    </b-col>
                  </b-row>
                </div>

              </b-modal>
            </div>
          </b-col>
          <!-- Col 2 -->
          <b-col
            sm="12"
            md="6"
            lg="4">
            <div class="services-block">
              <h2 v-b-modal.contentModal>Content<br>Creation</h2>
              <b-modal
                id="contentModal"
                class="modal-services"
                title="Content Creation">
                <div class="modal-container">
                  <p><img
                    src="~assets/images/content-primary-image.jpg"
                    class="img-right services-img"><strong>Content Creation.</strong> By far, content is the most effective tool in the inbound marketing arsenal. It takes many shapes: blogs, chat bots, video, social media posts, case studies, white papers, eBooks, etc. The way people search and purchase is constantly changing, so providing them a variety of content choice is vital. Having relevant, informative content for each stage of their buyers’ journey moves them further down your sales funnel. We help you focus on what’s important to your customers and target that content to answer their needs.</p>

                  <p><strong>CBD Digital Delivers:</strong></p>

                  <p><ul><li>Content marketing workshop</li>
                    <li>Content calendar</li>
                    <li>FAQs</li>
                    <li>Video consultation and promotion</li>
                  <li>Content creation: blogs, press releases, emails, case studies, eBooks, etc.</li></ul></p>
          </div></b-modal></div></b-col>
          <!-- Col 3 -->
          <b-col
            sm="12"
            md="6"
            lg="4">
            <div class="services-block">
              <h2 v-b-modal.socialModal>Social<br>Media</h2>
              <b-modal
                id="socialModal"
                class="modal-services"
                title="Social Media">
                <div class="modal-container">
                  <p><img
                    src="~assets/images/social-primary-image.jpg"
                    class="img-right services-img"><strong>Social Media.</strong> Social networks are instrumental in any B2B marketing strategy—and can have particular impact in the burgeoning legal cannabis market, as there’s so much information to be shared for all stakeholders. And ... there’s so much more available for B2B on social platforms than just cat videos and baby pictures! We’ll keep your connections up to date with the latest news, blogs, and industry perspectives using a comprehensive social media strategy. </p>

                  <p><strong>CBD Digital Delivers:</strong></p>

                  <p><ul><li> Pay-per-click ads (PPC)</li>
                    <li>Promotion of blogs and special content offers </li>
                    <li>Relevant audience perspectives </li>
                  <li>Company news </li></ul></p>
            </div></b-modal></div>
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
              v-b-popover.hover="'Wordpress is the world\'s most popular open-source CMS. It\'s a robust, fully customizable content management solution which gives allows for editng of your website copy with minimal learning curve.'"
              title="Wordpress CMS"
              class="wordpress-logo logo"><div>&nbsp;</div></div></b-col>
          <b-col
            sm="12"
            md="4"
            lg="3"
            xl="2"><div
              v-b-popover.hover="'Woocommerce is the leading e-commerce solution for Wordpress. Its scalability makes it a great fit for business small and large who want to begin selling products and services online, and best of all, it\'s open source.' "
              title="WooCommerce"
              class="woocommerce-logo logo"><div>&nbsp;</div></div></b-col>
          <b-col
            sm="12"
            md="4"
            lg="3"
            xl="2"><div
              v-b-popover.hover="'A2 Hosting offers fast, reliable shared and dedicated hosting, plus must-have add-ons like dedicated IPs and SSL certificates, all at competative prices.' "
              title="A2 Hosting"
              class="a2-logo logo"><div>&nbsp;</div></div></b-col>
          <b-col
            sm="12"
            md="4"
            lg="3"
            xl="2"><div
              v-b-popover.hover="'PHP is the open-source, server-side scripting language which powers the Wordpress sites we build, and MySQL is the database software it communicates with. These are the stable and reliable choices for backend web technologies we lean on most heavily for client web development.' "
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
              v-b-popover.hover="'Bootstrap is an open-source toolkit for quickly prototyping or building out HTML, CSS and JS. It speeds up development-time, has a great grid and compnent system, and is mobile-first.' "
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
            xl="2"><div class="survey-logo logo"><div>&nbsp;</div></div></b-col>
          <b-col
            sm="12"
            md="4"
            lg="3"
            xl="2"><div class="adobe-logo logo"><div>&nbsp;</div></div></b-col>
          <b-col
            sm="12"
            md="4"
            lg="3"
            xl="2"><div class="slack-logo logo"><div>&nbsp;</div></div></b-col>
          <b-col
            sm="12"
            md="4"
            lg="3"
            xl="2"><div class="moz-logo logo"><div>&nbsp;</div></div></b-col>
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
            <div id="cbd-hubspot-form">&nbsp;</div>
            <script
              charset="utf-8"
              type="text/javascript"
              src="//js.hsforms.net/forms/shell.js"/>
            <script charset="utf-8">
              hbspt.forms.create({
              portalId: '381132',
              formId: '4019399f-6e52-42ab-882b-27ccf9cf750d',
              target: '#cbd-hubspot-form',
              onFormSubmit($form, ctx){
              console.log('Submitted, biatch!');
              }
              });
            </script>
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
  </div>


  <!-- END SCROLLPSPY TEST -->
</template>

<script>
import Logo from '~/components/Logo.vue'
import Carousel from '~/components/Carousel.vue'

export default {
  components: {
    Logo,
    Carousel
  },
  data: function() {
    return {
      showUserGuide: false,
      showUserGuide1: false,
      showUserGuide2: false,
      cultivator: false,
      manufacturer: false,
      equipment: false,
      buttonTwoText: 'Just some text',
      cultivatorBtnTxt:
        'I need help with content/messaging to reach retailers and value-added resellers.',
      manufacturerBtnTxt:
        'I need help with content/messaging to reach retailers and dispensaries.',
      equipmentBtnTxt:
        'I need help with content/messaging to reach growers and retailers.',
      contactUsCopy:
        'We’re as excited about the advances being made in New England’s legal cannabis industry as you are! Experts in B2B marketing, we’re here to help you connect with the people behind the companies that are looking for your products and services. Contact us now &mdash; <strong>let’s grow your business!</strong>',
      additionalContactCopy:
        "Send us your contact info and we'll get started on a marketing plan just for you."
    }
  },
  computed: {
    choiceOne() {
      const choice = this.$store.state.choiceOne
      if (choice === 'nothing') {
        return choice
      } else if (choice === 'cult') {
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
      if (choice === 'cult') {
        this.cultivator = true
        this.buttonTwoText = this.cultivatorBtnTxt
        this.showUserGuide1 = false
        this.showUserGuide2 = true
      }
      if (choice === 'man') {
        this.manufacturer = true
        this.buttonTwoText = this.manufacturerBtnTxt
        this.showUserGuide1 = false
        this.showUserGuide2 = true
      }
      if (choice === 'equip') {
        this.equipment = true
        this.buttonTwoText = this.equipmentBtnTxt
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
  background-image: url('~assets/images/cbd-digital-home-banner-bg.jpg');
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
  background-image: url('~assets/images/hubspot-logo-gray.jpg');
}
.hubspot-logo > div {
  background-image: url('~assets/images/hubspot-logo-color.jpg');
}
.wordpress-logo {
  border-color: #20759b;
}
.wordpress-logo > div:hover {
  background-image: url('~assets/images/wordpress-logo-gray.png');
}
.wordpress-logo > div {
  background-image: url('~assets/images/wordpress-logo-color.jpg');
}
.woocommerce-logo {
  border-color: #9e5b90;
}
.woocommerce-logo > div:hover {
  background-image: url('~assets/images/woocommerce-logo-gray.jpg');
}
.woocommerce-logo > div {
  background-image: url('~assets/images/woocommerce-logo-color.jpg');
}
.a2-logo {
  border-color: #669940;
}
.a2-logo > div:hover {
  background-image: url('~assets/images/a2-hosting-logo-gray.jpg');
}
.a2-logo > div {
  background-image: url('~assets/images/a2-hosting-logo-color.jpg');
}
.php-logo {
  border-color: #6a7db6;
}
.php-logo > div:hover {
  background-image: url('~assets/images/php-logo-gray.jpg');
}
.php-logo > div {
  background-image: url('~assets/images/php-logo-color.jpg');
}
.vue-logo {
  border-color: #4cb986;
}
.vue-logo > div:hover {
  background-image: url('~assets/images/vue-logo-gray.jpg');
}
.vue-logo > div {
  background-image: url('~assets/images/vue-logo-color.jpg');
}
.bootstrap-logo {
  border-color: #563c7e;
}
.bootstrap-logo > div:hover {
  background-image: url('~assets/images/bootstrap-logo-gray.jpg');
}
.bootstrap-logo > div {
  background-image: url('~assets/images/bootstrap-logo-color.jpg');
}
.google-logo {
  border-color: #f37e20;
}
.google-logo > div:hover {
  background-image: url('~assets/images/google-analytics-logo-gray.jpg');
}
.google-logo > div {
  background-image: url('~assets/images/google-analytics-logo-color.jpg');
}
.survey-logo {
  border-color: #2db56e;
}
.survey-logo > div:hover {
  background-image: url('~assets/images/survey-monkey-logo-gray.jpg');
}
.survey-logo > div {
  background-image: url('~assets/images/survey-monkey-logo-color.jpg');
}
.adobe-logo {
  border-color: #d11f26;
}
.adobe-logo > div:hover {
  background-image: url('~assets/images/adobe-logo-color-gray.jpg');
}
.adobe-logo > div {
  background-image: url('~assets/images/adobe-logo-color.jpg');
}
.slack-logo {
  border-color: #85cee5;
}
.slack-logo > div:hover {
  background-image: url('~assets/images/slack-logo-gray.jpg');
}
.slack-logo > div {
  background-image: url('~assets/images/slack-logo-color.jpg');
}
.moz-logo {
  border-color: #2193d1;
}
.moz-logo > div:hover {
  background-image: url('~assets/images/moz-logo-gray.jpg');
}
.moz-logo > div {
  background-image: url('~assets/images/moz-logo-color.jpg');
}
.modal-services p {
  font-size: 19px;
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
  background-image: url('~assets/images/cbd-services-bg.png');
  cursor: pointer;
  margin-bottom: 30px;
}
.services-block:hover {
  background-image: url('~assets/images/cbd-services-bg-active.png');
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
}
</style>
