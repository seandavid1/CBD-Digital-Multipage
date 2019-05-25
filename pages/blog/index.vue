<template>
  <b-container class="default">
    <b-row>
      <b-col
        xl="12"
        lg="12"
        md="12"
        sm="12">
        <div>
          <h1>CBD Digital Blog</h1>
        </div>
      </b-col>
    </b-row>
    <b-row v-if="blog !== null">
        <b-col v-for="(blog, idx) in blogRSS" :key="idx"
        xl="4"
        lg="4"
        md="6"
        sm="12">
        <transition name="fade">
          <div>
            <b-card
              :img-src="BlogImage(idx)"
              img-alt="Image"
              img-top
              tag="article"
              style="max-width: 20rem;"
              class="mb-2">
              <h2><a :href="blog.link._text">{{blog.title._text}}</a></h2>
              <span class="author">{{ BlogAuthor(idx) }}</span>
              <p class="meta">   
                <span class="date">{{BlogDate(idx)}}</span>
                <social-sharing class="social-share" :url="blog.link._text"
                        :title="blog.title_text"
                        :description="BlogDescription(idx)"
                        :quote="BlogQuote(idx)"
                        hashtags="cbdMarketing, cbdDigital"
                        inline-template>
                        <div>
                            <network network="facebook">
                              <i class="fa fa-facebook-square"></i>
                            </network>
                            <network network="linkedin">
                              <i class="fa fa-linkedin-square"></i>
                            </network>
                            <network network="twitter">
                              <i class="fa fa-twitter-square"></i>
                            </network>
                        </div>
                  </social-sharing>
                </p>
                <div class="blog-h3" v-if="BlogH3" v-html="BlogH3(idx)">
                </div>
                <div
                  class="card-text blog"
                  v-html="BlogDescription(idx)"/>
                <b-button
                  :href="blog.link._text"
                  variant="primary">Read More</b-button>
            </b-card>
          </div>
        </transition>
      </b-col>
    </b-row>
    <!-- <b-row>
      <b-col>
        <transition name="fade">
          <div>
            <div class="blog-pagination">
              <b-pagination-nav
                :number-of-pages="10"
                v-model="currentPage"
                base-url="#" />
              <div class="mt-4">currentPage: {{ currentPage }}</div>
            </div>
          </div>
        </transition>
      </b-col>
    </b-row> -->
  </b-container>
</template>

<script>
export default {
  components: {},
  head () {
    return {
      title: 'The CBD Digital Group Blog',
      meta: [
        { hid: 'description', name: 'description', content: 'CND Digital Group is committed to bringing you the latest news and events surrounding CBD and Cannabis marketing, plus our own insider tips and tricks on how to promote your CBD or cannabis business.' }
      ]
    }
  },
  data() {
    return {
      errors: [],
      blogFeed: []
    }
  },
  computed: {
    custom() {
      return this.$store.state.pagesACF.find(field => field.id === 5)
    },
    about() {
      return this.$store.state.about
    },
    blog() {
      return this.$store.state.blog
    },
    blogRSS() {
      return this.$store.state.blog.rss.channel.item
    }
  },
  created() {
    // this.$store.dispatch('getPagesACF')
    // this.$store.dispatch('getPages')
    // this.$store.dispatch('getAboutUs')
    this.$store.dispatch('getBlogs')
  },
  methods: {
    BlogDescription(num) {
      var description = this.$store.state.blog.rss.channel.item[num].description
        ._text
      if (description) {
        var descriptionIndex = description.indexOf('</div>')
        descriptionIndex += 6
        var cleanDescription = description.substring(descriptionIndex)
        var h3Index = cleanDescription.indexOf('</h3>')
        if (h3Index) {
          var descriptionOnly = cleanDescription.substring(h3Index)
          var periodIndex = descriptionOnly.indexOf('.')
          periodIndex += 1
          var firstSentence = descriptionOnly.substring(0, periodIndex)
          if (firstSentence.length > 163) {
            var truncated = firstSentence.substring(0, 163)
            var spaceIndex = truncated.lastIndexOf(' ')
            var toBeContinued = truncated.substring(0, spaceIndex)
            toBeContinued += '...'
            return toBeContinued
          }
          else {
            return firstSentence
          }
        }
        else {
          return cleanDescription
        }
      }
      
    },
    BlogDate(num) {
      var date = this.$store.state.blog.rss.channel.item[num].pubDate
        ._text
      if (date) {
        var dateIndex = date.indexOf(',')
        dateIndex += 2
        var colonIndex = date.indexOf(':')
        colonIndex -= 2
        var cleanDate = date.substring(dateIndex, colonIndex)
      }
      return cleanDate
    },
    BlogAuthor(num) {
      var creator = this.$store.state.blog.rss.channel.item[num]['dc:creator']
      if (creator) {
        var author = creator._text
        var author_text = 'By ' + author
      }
      return author_text
    },
    BlogImage(num) {
      var description = this.$store.state.blog.rss.channel.item[num].description
        ._text
        if (description) {
          var wrapperIndex = description.indexOf('</div>')
          var imageWrapper = description.substring(0, wrapperIndex)
          var imageIndex1 = imageWrapper.indexOf('src')
          imageIndex1 += 5
          var imageIndex2 = imageWrapper.indexOf('alt')
          imageIndex2 -= 2
          var image = imageWrapper.substring(imageIndex1, imageIndex2)
        }
      return image
    },
    BlogLink(num) {
      var link = this.$store.state.blog.rss.channel.item[num].link._text
      return link
    },
    BlogH3(num) {
      var description = this.$store.state.blog.rss.channel.item[num].description
        ._text
      if (description) {
        var descriptionIndex = description.indexOf('</div>')
        descriptionIndex += 6
        var cleanDescription = description.substring(descriptionIndex)
        var h3Index = cleanDescription.indexOf('</h3>')
        h3Index += 5
        if (h3Index) {
          var h3 = cleanDescription.substring(0, h3Index)
        }
      }
      return h3
    },
    BlogQuote(num) {
      var description = this.$store.state.blog.rss.channel.item[num].description
        ._text
      if (description) {
        var descriptionIndex = description.indexOf('</div>')
        descriptionIndex += 6
        var cleanDescription = description.substring(descriptionIndex)
        var h3Index = cleanDescription.indexOf('</h3>')
        var h3Begin = cleanDescription.indexOf('<h3>')
        h3Begin += 4
        h3Index
        if (h3Index) {
          var quote = cleanDescription.substring(h3Begin, h3Index)
        }
      }
      return quote
    },
  },
  layout: 'default'
}
</script>

<style scoped>
img.hs-featured-image {
  display: none !important;
}
article > img {
  max-height: 210px;
}
h4.card-title {
  font-size: 18px;
  font-weight: bold;
  height: 61px;
}
p.card-text {
  max-height: 165px;
  overflow: hidden;
}
article.card {
  margin: 0 auto;
}
.blog-pagination {
  text-align: center;
  float: left;
  width: 100%;
}
.blog-pagination nav {
  margin: 0 auto;
  width: 310px;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 1s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
h2 {
    font-size: 29px;
    font-weight: bold;
    margin-top: 0px;
    margin-bottom: 5px;
    letter-spacing: -0.5px;
    line-height: 28px;
}
p.meta {
    font-size: 14px;
    font-weight: bold;
    color: #444;
    border-top: 1px solid #ccc;
    padding: 2px 8px;
    border-bottom: 1px solid #ccc;
    height: 29px;
    background-color: #ccc;
}
span.date {
    float: left;
    text-transform: uppercase;
    font-size: 14px;
    margin-top: 1px;
    letter-spacing: -0.3px;
}
.social-share {
    float: right;
}
span.author {
    font-size: 13px;
    font-weight: bold;
    text-align: right;
    width: 100%;
    display: block;
    margin-bottom: 11px;
    color: #666;
    text-transform: uppercase;
}

</style>
