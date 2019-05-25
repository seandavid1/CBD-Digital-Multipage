<template>
  <div>
    <transition name="fade">
          <div
            v-if="custom"
            v-html="custom.content.rendered"/>
        </transition>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  pageTitle: 'Content Creation',
  asyncData ({ params }) {
    return axios.get(`https://www.cbddigitalgroup.com/wp/wp-json/wp/v2/pages/46`)
    .then((res) => {
      return { 
        metaDescription: res.data.yoast_meta.yoast_wpseo_metadesc, 
        metaTitle: res.data.yoast_meta.yoast_wpseo_title
      }
    })
  },
   components: {
  },
  computed: {
    custom() {
      var custom = this.$store.state.pages.find(field => field.id === 46)
      return custom
    }
  },
  head() {
    return {
      title: this.metaTitle,
      meta: [
        {hid:  'description', name: 'description', content: this.metaDescription }
      ]
    }
  },
  layout: 'full_width'
}
</script>