<template>
  <div>
    <b-carousel
      id="carousel1"
      :interval="4000"
      v-model="slide"
      style="text-shadow: 1px 1px 2px #333;"
      controls
      indicators
      background="#ababab"
      img-width="100%"
      img-height="480"
      @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd"
    >

      <!-- Text slides with image -->
      <b-carousel-slide>
        <img
          slot="img"
          class="d-block img-fluid w-100"
          width="1024"
          height="480"
          src="~/assets/slider1.jpg"
          alt="image slot">
        <h1>Hello world!</h1>
      </b-carousel-slide>

      <!-- Slides with custom text -->
      <b-carousel-slide>
        <img
          slot="img"
          class="d-block img-fluid w-100"
          width="1024"
          height="480"
          src="~/assets/slider2.jpg"
          alt="image slot">
        <h1>Hello world!</h1>
      </b-carousel-slide>

      <!-- Slides with img slot -->
      <!-- Note the classes .d-block and .img-fluid to prevent browser default image alignment -->

    </b-carousel>

    <!-- <p class="mt-4">
      Slide #: {{ slide }}<br>
      Sliding: {{ sliding }}
    </p> -->

  </div>
</template>

<script>
export default {
  data() {
    return {
      slide: 0,
      sliding: null
    }
  },
  methods: {
    onSlideStart(slide) {
      this.sliding = true
    },
    onSlideEnd(slide) {
      this.sliding = false
    }
  }
}
</script>
<!-- carousel-1.vue -->
