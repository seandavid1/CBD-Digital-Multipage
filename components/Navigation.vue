<template>
  <b-navbar
    v-b-scrollspy:nav-scroller
    toggleable="md"
    type="light"
    variant="primary-inverse"
    fixed="top">

    <b-navbar-brand
      :to="'/?segment=' + urlSegmentOne + '&help=' + urlSegmentTwo"><logo/></b-navbar-brand>

    <b-navbar-toggle target="nav_collapse"/>

    <b-collapse
      id="nav_collapse"
      is-nav>

      <b-navbar-nav>
        <!-- <b-nav-item :to="'/about?segment=' + urlSegmentOne + '&help=' + urlSegmentTwo" >About CBD Digital </b-nav-item> -->
        <b-nav-item-dropdown text="Services We Provide">
          <b-dropdown-item :to="'/branding?segment=' + urlSegmentOne + '&help=' + urlSegmentTwo">Branding</b-dropdown-item>
          <b-dropdown-item :to="'/marketing?segment=' + urlSegmentOne + '&help=' + urlSegmentTwo">Marketing</b-dropdown-item>
          <b-dropdown-item :to="'/graphic-design?segment=' + urlSegmentOne + '&help=' + urlSegmentTwo">Graphic Design</b-dropdown-item>
          <b-dropdown-item :to="'/web-design-and-development?segment=' + urlSegmentOne + '&help=' + urlSegmentTwo">Web Design and Development</b-dropdown-item>
          <b-dropdown-item :to="'/content-creation?segment=' + urlSegmentOne + '&help=' + urlSegmentTwo">Content Creation</b-dropdown-item>
          <b-dropdown-item :to="'/social-media?segment=' + urlSegmentOne + '&help=' + urlSegmentTwo">Social Media</b-dropdown-item>
        </b-nav-item-dropdown>
        <b-nav-item to="/blog">CBD Digital Blog</b-nav-item>
        <b-nav-item :to="'/contact-us?segment=' + urlSegmentOne + '&help=' + urlSegmentTwo">Contact Us</b-nav-item>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  computed: {
    urlSegmentOne() {
        return this.$store.state.choiceOne 
      },
    urlSegmentTwo() {
      return this.$store.state.choiceTwo
    }
  }
}
</script>

<style scoped>
a {
  color: rgba(0, 0, 0, 0.5);
}
</style>
