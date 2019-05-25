<template>
  <div>
    <h1>{{metaDescription}}</h1>
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
  asyncData ({ params }) {
    return axios.get(`http://www.cbddigitalgroup.com/wp/wp-json/wp/v2/pages/24`)
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
      var custom = this.$store.state.pages.find(field => field.id === 5)
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
