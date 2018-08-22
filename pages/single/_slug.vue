<template>
  <div>

    <!-- COIDEA:header START -->
    <app-header/>
    <!-- COIDEA:header END -->


    <!-- COIDEA:main START -->
    <main v-for="(item, index) of items" :key="index" v-if="item.slug == itemSlug">
      
      <!-- COIDEA:main:section:headline START -->
      <section class="headline">
        <div class="container">
          <div class="row">
            <div class="title-subtitle">
            
              <!-- COIDEA:main:section:headline:title START -->
              <h1 class="title">
                {{ item.headline }}
              </h1>
              <!-- COIDEA:main:section:headline:title END -->

              <!-- COIDEA:main:section:headline:subtitle START -->
              <h2 class="subtitle" v-html="item.excerpt"></h2>
              <!-- COIDEA:main:section:headline:subtitle END -->

            </div>
          </div>
        </div>
      </section>
      <!-- COIDEA:main:section:headline END -->

      <!-- COIDEA:main:main START -->
      <div class="main">
        <!-- COIDEA:main:section:article START -->
        <section class="single">
          <div class="container">
            <div class="row">
              
              <article>

                <div class="main-image">
                  <img :src="item.image" :alt="'COIDEA - ' + item.headline + 'Main Image'" />
                </div>

                <div class="date">
                  <div>
                    <p>In <nuxt-link :to="'/categories/' + item.category" :title="item.category">{{ item.category }}</nuxt-link> by <nuxt-link to="/about" :title="item.author">{{ item.author }}</nuxt-link> on {{ item.date }}</p>
                  </div>
                </div> 

                <div class="excerpt-article">
                  <p>Today we’d like to show you a little slideshow design with a “triple panel” layout. The infinite
                      slideshow shows a preview of the next and previous slide on both sides of the page. When
                      navigating we use a reveal effect for all three images and animate the titles. The animations
                      are powered by TweenMax.</p>
                </div>

                <div class="ad">
                  <img src="~/assets/images/temp/article-ad.png" alt="" />
                  <span>Advertisement</span>
                </div>

                <div class="content">
                  <h2>Creating the structure</h2>
                  <p>We’ve been publishing in our library some nice mask effects powered by SVG properties. 
                    This time we took advantage of the PNG transparencies to zoom through the mask layer, into 
                    a project background image.</p>
                </div>

                <div class="attention">
                  <p><span>Note that we use modern CSS properties<br>that might not be supported in older browsers.</span></p>
                  <span>Attention</span>
                </div>

                <div class="content">
                  <p>If you want to change the color of the .png masks, you can easily do it in Photoshop 
                    (or any other graphic tool) by applying a color overlay to the whole image layer.</p>
                </div>

                <div class="image">
                  <img src="~/assets/images/temp/article-image.jpg" alt="" />
                  <span>Hovering</span>
                </div>

                <div class="content">
                  <p>When navigating, we animate a reveal element that covers each image. Depending on which 
                    direction we are navigating, we make the revealer appear from bottom or from the top. 
                    All title elements have an animation except for the “Explore” link.</p>
                </div>

                <div class="highlight">
                  <pre v-highlightjs><code class="html">
&lt;section class="project-1 cd-project-mask"&gt;
   &lt;h1&gt;Project Name&lt;/h1&gt;
   &lt;div class="featured-image"&gt;&lt;/div&gt;
   &lt;div class="mask"&gt;
      &lt;img src="img/mask-01.png" alt="mask"&gt;
      &lt;span class="mask-border mask-border-top"&gt;&lt;/span&gt;
      &lt;span class="mask-border mask-border-bottom"&gt;&lt;/span&gt;
      &lt;span class="mask-border mask-border-left"&gt;&lt;/span&gt;
      &lt;span class="mask-border mask-border-right"&gt;&lt;/span&gt;
   &lt;/div&gt;

   &lt;a href="#0" class="project-trigger"&gt;Explore Project&lt;/a&gt;

   &lt;a href="#0" class="cd-scroll cd-img-replace"&gt;Scroll down&lt;/a&gt;

   &lt;div class="cd-project-info" data-url="project-1"&gt;
      &lt;!-- content loaded using js --&gt;
   &lt;/div&gt;

   &lt;a href="#0" class="project-close cd-img-replace"&gt;Close Project&lt;/a&gt;
&lt;/section&gt; &lt;!-- .cd-project-mask --&gt;

&lt;section class="project-2 cd-project-mask"&gt;
   &lt;!-- content here --&gt;
&lt;/section&gt;

&lt;!-- other sections here --&gt;</code></pre>
                  <span>HTML Structure</span>
                </div>

                <div class="content">
                  <p>When navigating, we animate a reveal element that covers each image. Depending on which direction we are navigating, we make the revealer appear from bottom or from the top. All title elements have an animation except for the “Explore” link.</p>

                  <p>When navigating, we animate a reveal element that covers each image. Depending on which direction we are navigating, we make the revealer appear from bottom or from the top. All title elements have an animation except for the “Explore” link.</p>

                  <p>When navigating, we animate a reveal element that covers each image. Depending on...</p>
                </div>

              </article>

              <div class="view-all">
                <nuxt-link to="/" class="load-more" title="DOWNLOAD">DOWNLOAD</nuxt-link>
                <nuxt-link to="/" class="load-more" title="DEMO">DEMO</nuxt-link>
              </div>

            </div>
          </div>
        </section>
        <!-- COIDEA:main:section:article END -->  

        <!-- COIDEA:main:main START -->
        <app-sidebar />
        <!-- COIDEA:main:main END -->

      </div>
      <!-- COIDEA:main:main END -->

      <!-- COIDEA:main:section:categories START -->
      <section class="categories">
        <div class="container">
          <div class="row">
            <div class="categories">
            
              <!-- COIDEA:main:section:categories:card START -->
              <div class="card" v-for="(category, index) in categories" :key="index">
                <nuxt-link :to="'/categories/' + category.slug" :title="category.slug">
                  <h4>{{ category.slug }}</h4>
                  <img :src="category.icon" :alt="category.slug" />
                </nuxt-link>
              </div>
              <!-- COIDEA:main:section:categories:card END -->

            </div>
          </div>
        </div>
      </section>
      <!-- COIDEA:main:section:categories END -->
      

      

    </main>
    <!-- COIDEA:main END -->

    <!-- COIDEA:footer START -->
    <app-footer/>
    <!-- COIDEA:footer END -->

  </div>
</template>


<script>
  import AppHeader from '~/components/AppHeader.vue'
  import AppFooter from '~/components/AppFooter.vue'
  import AppSidebar from '~/components/AppSidebar.vue'

  // temp images
  import image1 from '~/assets/images/temp/real-article-1.jpg'
  import image2 from '~/assets/images/temp/real-article-2.jpg'
  import image3 from '~/assets/images/temp/real-article-3.jpg'
  import image4 from '~/assets/images/temp/real-article-4.jpg'
  import image5 from '~/assets/images/temp/real-article-5.jpg'

  // temp images categories
  import icon1 from '~/assets/images/design/icon-tutorials.png'
  import icon2 from '~/assets/images/design/icon-playground.png'
  import icon3 from '~/assets/images/design/icon-blueprint.png'
  import icon4 from '~/assets/images/design/icon-inspiration.png'
  import icon5 from '~/assets/images/design/icon-freebies.png'

  export default {
    data() {
      return {
        itemSlug: this.$route.params.slug,
        items: [
          {
            id: 1,
            headline: 'Lorem ipsum sit dolor amet',
            slug: 'lorem-ipsum-sit-dolor-amet',
            category: 'brainstorms',
            category_id: 3,
            author: 'Mirza Hodzic',
            date: 'July 25, 2018',
            image: image1,
            permalink: '/single'
          },
          {
            id: 2,
            headline: 'Amet dolor sit ipsum lorem',
            slug: 'amet-dolor-sit-ipsum-lorem',
            category: 'tutorials',
            category_id: 3,
            author: 'Mirza Hodzic',
            date: 'July 20, 2018',
            image: image2,
            permalink: '/single'
          },
          {
            id: 3,
            headline: 'Amet dolor sit',
            slug: 'amet-dolor-sit',
            category: 'abstract',
            category_id: 3,
            author: 'Mirza Hodzic',
            date: 'July 20, 2018',
            image: image3,
            permalink: '/single'
          },
          {
            id: 4,
            headline: 'Sit dolor amet',
            slug: 'sit-dolor-amet',
            category: 'resources',
            category_id: 3,
            author: 'Mirza Hodzic',
            date: 'July 20, 2018',
            image: image4,
            permalink: '/single'
          },
          {
            id: 5,
            headline: 'Dolor amet sit',
            slug: 'dolor-amet-sit',
            category: 'gifts',
            category_id: 3,
            author: 'Mirza Hodzic',
            date: 'July 20, 2018',
            image: image5,
            permalink: '/single'
          }
        ],
        categories: [
          {
            id: 1,
            slug: 'brainstorms',
            description: 'Gummies topping bear claw danish cookie gummi bears. Pudding marshmallow chocolate bar dragée croissant wafer jelly.',
            icon: icon1
          },
          {
            id: 2,
            slug: 'tutorials',
            description: 'Gummies topping bear claw danish cookie gummi bears. Pudding marshmallow chocolate bar dragée croissant wafer jelly.',
            icon: icon2
          },
          {
            id: 3,
            slug: 'abstract',
            description: 'Gummies topping bear claw danish cookie gummi bears. Pudding marshmallow chocolate bar dragée croissant wafer jelly.',
            icon: icon3
          },
          {
            id: 4,
            slug: 'resources',
            description: 'Gummies topping bear claw danish cookie gummi bears. Pudding marshmallow chocolate bar dragée croissant wafer jelly.',
            icon: icon4
          },
          {
            id: 5,
            slug: 'gifts',
            description: 'Gummies topping bear claw danish cookie gummi bears. Pudding marshmallow chocolate bar dragée croissant wafer jelly.',
            icon: icon5
          }
        ],
        limitationList: 3
      }
    },
    methods: {
      updateLimitation(limitationList){
        if ( this.limitationList >= this.items.length) {
          this.limitationList = 3;
        } else {
          // this.limitationList = this.events.length
          this.limitationList += 2;
        }
      }
    },
    components: {
      AppHeader,
      AppFooter,
      AppSidebar
    }
  }
</script>


<style lang="scss" scoped>
  
  @import '~/assets/scss/styles.scss';

  main {
    @include position--default();
    width: 100%;
    height: auto;
    overflow: hidden;
    section {
      &.headline {
        .container {
          @include position--default();
          width: 100%;
          height: auto;
          overflow: hidden;
          margin: 0 auto;
          .row {
            padding: 0 .75em;
            .title-subtitle {
              padding: 0 16px;
              /*
              @include maxquery( 992px ) {
                padding: 0 .75em;
              }
              */
              h1 {
                padding: 0;
                margin: 0;
                &.title {
                  @include position--default();
                  width: 100%;
                  max-width: 768px;
                  height: auto;
                  font-size: 60px;
                  line-height: 70px;
                  font-weight: 200;
                  span {
                    position: relative;
                    transition: all .2s ease-in-out;
                    -webkit-transition: all .2s ease-in-out;
                    transition-delay: .25;
                    &::after {
                      background-color: $blue;
                      @include pseudo--ba();
                      width: 100%;
                      width: calc(100% + 16px);
                      height: 28px;
                      bottom: 0px; left: -8px;
                      z-index: -1;
                      opacity: .3;
                      transition: all .25s ease-in-out;
                      -webkit-transition: all .25s ease-in-out;
                    }
                  }
                  &:hover {
                    span {
                      // color: $white;
                      &::after {
                        height: 68px;
                        // opacity: 1;
                      }
                    }
                  }
                }
              }
              h2 {
                max-width: 768px;
                padding: 0;
                margin: 0;
                &.subtitle {
                  @include position--default();
                  width: 100%;
                  height: auto;
                  padding-top: 22px;
                  font-size: 18px;
                  line-height: 28px;
                  font-weight: 700;
                }
              }
            }
          }
        }
      }
      &.categories {
        background-color: $lightblue;
        .container {
          @include position--default();
          width: 100%;
          max-width: 1630px;
          height: auto;
          overflow: hidden;
          margin: 0 auto;
          padding: 92px 0;
          .row {
            padding: 0;
            .categories {
              @include position--default();
              padding: 0 16px;
              /*
              @include maxquery( 768px ) {
                padding: 0 .75em;
              }
              */
              .card {
                @include position--default();
                background-color: $white;
                width: 18%;
                width: calc( 20% - 32px );
                height: 260px;
                margin: 16px;
                float: left;
                transition: all .45s ease-in-out;
                -webkit-transition: all .45s ease-in-out;
                @include maxquery( 992px ) {
                  width: calc( 100% - 32px );
                }
                a {
                  @include position--default();
                  width: 100%;
                  height: 260px;
                  color: inherit;
                  text-decoration: none;
                  transition: all .45s ease-in-out;
                  -webkit-transition: all .45s ease-in-out;
                  h4 {
                    @include position--default(block, absolute);
                    width: 100%;
                    height: auto;
                    margin: 0; padding: 0;
                    font-size: 24px;
                    line-height: 24px;
                    font-weight: 200;
                    text-align: center;
                    top: 50%;
                    transform: translateY( -50% );
                    transition: all .45s ease-in-out;
                    -webkit-transition: all .45s ease-in-out;
                  }
                  img {
                    @include position--default(block, absolute);
                    width: 120px;
                    height: auto;
                    top: 50%; left: 50%;
                    transform: translate( -50%, 25% );
                    transition: all .35s ease-in-out;
                    -webkit-transition: all .35s ease-in-out;
                    transition-delay: 0.15;
                  }
                }
                &:hover {
                  box-shadow: 0 24px 36px rgba(0,0,0,0.045), 0 10px 10px rgba(0,0,0,0.042);
                  a {
                    color: $blue;
                    h4 {
                      top: 48px;
                    }
                    img {
                      top: 70px;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    .main {
      background-color: $white;
      @include position--default();
      width: 100%;
      height: auto;
      float: left;
      overflow: hidden;
      section {
        &.single {
          @include position--default();
          width: 100%;
          max-width: calc( 100% - 352px );
          margin: 0; margin-top: 82px;
          padding: 0;
          float: left;
          @include maxquery( 768px ) {
            max-width: 100%;
          }
          .container {
            @include position--default();
            width: 100%;
            height: auto;
            overflow: hidden;
            margin: 0 auto;
            z-index: 1;
            .row {
              padding: 0 .75em;
              article {
                @include position--default();
                width: 100%;
                height: auto;
                // overflow: hidden;
                margin: 0 18px;
                .main-image {
                  @include position--default();
                  width: 100%;
                  width: calc( 100% - 32px );
                  height: auto;
                  overflow: hidden;
                  img {
                    @include position--default();
                    width: 100%;
                    min-width: 100%;
                    max-width: 100%;
                    height: auto;
                  }
                }
                .date {
                  @include position--default();
                  width: 100%;
                  width: calc( 100% - 32px );
                  height: auto;
                  overflow: hidden;
                  div {
                    margin: 0;
                    padding: 0;
                    font-size: 18px;
                    line-height: 28px;
                    z-index: 2;
                    p {
                      position: relative;
                      margin: 0;
                      padding: 16px;
                      white-space: nowrap;
                      overflow: hidden;
                      text-overflow: ellipsis;
                      z-index: 1;
                      a {
                        color: inherit;
                        font-weight: 700;
                        text-decoration: none;
                        transition: all .45s ease-in-out;
                        -webkit-transition: all .45s ease-in-out;
                        &:hover {
                          color: $blue;
                        }
                      }
                    }
                  }
                  &::after {
                    background-color: $blue;
                    @include pseudo--ba();
                    width: 100%;
                    max-width: 992px;
                    height: 10px;
                    bottom: 20px; left: 0;
                    z-index: 0;
                    opacity: .3;
                  }
                }
                .excerpt-article {
                  @include position--default();
                  width: 100%;
                  max-width: 992px;
                  width: calc( 100% - 32px );
                  height: auto;
                  overflow: hidden;
                  margin-bottom: 16px;
                  @include maxquery( 992px ) {
                    max-width: 90%;
                    max-width: calc( 100% - 32px );
                  }
                }
                .ad {
                  @include position--default();
                  width: 100%;
                  max-width: 992px;
                  width: calc( 100% - 32px );
                  height: auto;
                  margin-bottom: 48px;
                  img {
                    @include position--default();
                    width: 100%;
                    min-width: 100%;
                    max-width: 100%;
                    height: auto;
                    z-index: 2;
                  }
                  &::before {
                    background-color: $blue;
                    @include pseudo--ba();
                    width: 100%;
                    height: 100%;
                    bottom: -32px;
                    left: -32px;
                    z-index: 1;
                    opacity: .3;
                  }
                  span {
                    @include position--default(block, absolute);
                    bottom: -24px; left: 16px;
                    color: $black;
                    font-size: 14px;
                    line-height: 14px;
                    font-weight: 700;
                    text-transform: uppercase;
                    z-index: 2;
                  }
                }
                .content {
                  @include position--default();
                  width: 100%;
                  max-width: 992px;
                  width: calc( 100% - 32px );
                  height: auto;
                  overflow: hidden;
                  margin-bottom: 16px;
                }
                .attention {
                  @include position--default();
                  width: 100%;
                  max-width: 992px;
                  width: calc( 100% - 32px );
                  height: auto;
                  margin-bottom: 48px;
                  span {
                    @include position--default(block, absolute);
                    bottom: -24px; left: 16px;
                    color: $black;
                    font-size: 14px;
                    line-height: 14px;
                    font-weight: 700;
                    text-transform: uppercase;
                    z-index: 2;
                  }
                  p {
                    background-color: $white;
                    @include position--default();
                    width: 100%;
                    min-width: 100%;
                    max-width: 100%;
                    height: auto;
                    z-index: 2;
                    span {
                      @include position--default();
                      max-width: 992px;
                      width: calc( 100% - 32px );
                      font-size: 18px;
                      line-height: 28px;
                      font-weight: 700;
                      text-transform: inherit;
                      left: inherit;
                      bottom: inherit;
                      padding: 16px;
                    }
                  }
                  &::before {
                    background-color: $blue;
                    @include pseudo--ba();
                    width: 100%;
                    height: 100%;
                    bottom: -32px;
                    left: -32px;
                    z-index: 1;
                    opacity: .3;
                  }
                }
                .image {
                  @include position--default();
                  width: 100%;
                  max-width: 992px;
                  width: calc( 100% - 32px );
                  height: auto;
                  margin-bottom: 48px;
                  img {
                    @include position--default();
                    width: 100%;
                    min-width: 100%;
                    max-width: 100%;
                    height: auto;
                    z-index: 2;
                  }
                  &::before {
                    background-color: $blue;
                    @include pseudo--ba();
                    width: 100%;
                    height: 100%;
                    bottom: -32px;
                    left: -32px;
                    z-index: 1;
                    opacity: .3;
                  }
                  span {
                    @include position--default(block, absolute);
                    bottom: -24px; left: 16px;
                    color: $black;
                    font-size: 14px;
                    line-height: 14px;
                    font-weight: 700;
                    text-transform: uppercase;
                    z-index: 2;
                  }
                }
                .highlight {
                  @include position--default();
                  width: 100%;
                  max-width: 992px;
                  width: calc( 100% - 32px );
                  height: auto;
                  margin-bottom: 48px;
                  span {
                    @include position--default(block, absolute);
                    bottom: -24px; left: 16px;
                    color: $black;
                    font-size: 14px;
                    line-height: 14px;
                    font-weight: 700;
                    text-transform: uppercase;
                    z-index: 2;
                  }
                  pre {
                    font-family: 'Source Code Pro', monospace;
                    background-color: $white;
                    @include position--default();
                    width: 100%;
                    max-width: 992px;
                    width: calc( 100% - 32px );
                    height: auto;
                    z-index: 2;
                    padding: 0 16px;
                    &:first-line {
                      line-height: 0px;
                    }
                    span {
                      @include position--default();
                      max-width: 992px;
                      width: calc( 100% - 32px );
                      font-size: 18px;
                      line-height: 28px;
                      font-weight: 700;
                      text-transform: inherit;
                      left: inherit;
                      bottom: inherit;
                      padding: 16px;
                    }
                  }
                  &::before {
                    background-color: $blue;
                    @include pseudo--ba();
                    width: 100%;
                    height: 100%;
                    bottom: -32px;
                    left: -32px;
                    z-index: 1;
                    opacity: .3;
                  }
                }
              }
              .view-all {
                @include position--default();
                width: calc( 100% - 32px );
                height: auto;
                overflow: hidden;
                padding: 32px 16px;
                @include maxquery( 992px ) {
                  width: 90%;
                  width: calc( 100% - 1.5em );
                  padding: 0 .75em;
                }
                .load-more {
                  @include position--default();
                  background-color: $blue;
                  width: 48%;
                  width: calc( 50% - 16px );
                  height: 128px;
                  color: $white;
                  font-size: 32px;
                  line-height: 128px;
                  font-weight: 200;
                  text-align: center;
                  text-decoration: none;
                  float: left;
                  margin-right: 8px;
                  cursor: pointer;
                  outline: 0px none;
                  outline: 0px;
                  transition: all .45s ease-in-out;
                  -webkit-transition: all .45s ease-in-out;
                  box-shadow: 0 7px 13px rgba(0,0,0,0.02), 0 7px 12px rgba(0,0,0,0.025);
                  @include maxquery( 992px ) {
                    width: 100%;
                    margin: 0 0 32px 0;
                  }
                  &:hover {
                    background-color: $darkblue;
                    box-shadow: 0 24px 36px rgba(0,0,0,0.045), 0 10px 10px rgba(0,0,0,0.042);
                  }
                  &:nth-child(2) {
                    background-color: $darkblue;
                    margin-left: 8px;
                    margin-right: 0;
                    float: right;
                    &:hover {
                      background-color: $blue;
                      box-shadow: 0 24px 36px rgba(0,0,0,0.045), 0 10px 10px rgba(0,0,0,0.042);
                    }
                  }
                }
                p {
                  @include position--default();
                  width: 100%;
                  height: auto;
                  overflow: hidden;
                  font-size: 14px;
                  line-height: 14px;
                  font-weight: 400;
                  text-align: center;
                  padding: 48px 0;
                }
              }
            }
          }
          &::after {
            background-color: $lightblue;
            @include pseudo--ba();
            width: 100%;
            height: 100%;
            height: calc(100% - 216px);
            top: 108px; right: 0; left: 0;
            z-index: 0;
          }
        }
      }
    }   
  }

</style>

