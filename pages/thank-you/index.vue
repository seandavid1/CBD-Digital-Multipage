<template>
  <div>
    <b-container class="default contact-us">
        <b-row>
            <h1>Thank you</h1>
        </b-row>
      <b-row>
        <b-col
          xl="12"
          lg="12"
          md="12"
          sm="12">
          <div>
            
            <div class="wordpress-content">
              <transition name="fade">
                <div
                  v-if="custom"
                  v-html="custom.content.rendered"/>
              </transition>
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

  </div>

</template>

<script>
import BottomForm from '~/components/BottomForm.vue'
export default {
   components: {
    BottomForm
  },
  data() {
    return {
      errors: []
    }
  },
  computed: {
    custom() {
      return this.$store.state.pages.find(field => field.id === 52)
    },
    about() {
      return this.$store.state.about
    },
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
    aboutOne() {
      const choice = this.$store.state.choiceOne
      if (choice === 'nothing') {
        return choice
      } else if (choice === 'cult') {
        return 'cannabis cultivator/grower'
      } else if (choice === 'man') {
        return 'cannabis-infused products manufacturer'
      } else if (choice === 'equip') {
        return 'cannabis equipment or service provider'
      }
    },
    aboutTwo() {
      return this.$store.state.choiceTwo
    },
    customMessage() {
      var choiceOne = this.$store.state.choiceOne
      var choiceTwo = this.$store.state.choiceTwo
      var choiceTwoMod = ''
      if (choiceTwo) {
        var choiceTwoMod = choiceTwo.replace('I', 'you')
      }
      var response = ''
      if (choiceOne === null && choiceTwo === null) {
        return '<strong>Tell us more about you:</strong>'
      } else {
        if (choiceOne === 'cult') {
          response = 'You are a cannabis cultivator or grower'
        } else if (choiceOne === 'man') {
          response = 'You are a cannabis-infused products manufacturer'
        } else if (choiceOne === 'equip') {
          response = 'You are a cannabis equipment or service provider'
        }
        if (choiceTwo === null) {
          response += '. <br><br><strong>Tell us more about you:</strong>'
          return response
        } else if (choiceTwo === 'logo') {
          response +=
            ', and are in need of help with a new logo or mission statement.'
          return response
        } else if (choiceTwo === 'web') {
          response +=
            ', and are in need of help with website design and maintenance.'
          return response
        } else {
          response += ', and '
          response += choiceTwoMod
          return response
        }
      }
    }
  },
  created() {
    //this.$store.dispatch('getPagesACF')
    this.$store.dispatch('getPages')
    //this.$store.dispatch('getAboutUs')
  },
  methods: {
    changeForm() {
      console.log('changed')
      jquery('h1').css('display', 'none')
    }
  },
  layout: 'default'
}
</script>

<style>
</style>


