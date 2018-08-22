<template>
  <div>

    <!-- COIDEA:header START -->
    <app-header/>
    <!-- COIDEA:header END -->


    <!-- COIDEA:main START -->
    <main v-for="(category, index) of categories" :key="index" v-if="category.slug == catSlug">

      <!-- COIDEA:main:section:headline START -->
      <section class="headline">
        <div class="container">
          <div class="row">
            <div class="title-subtitle">
            
              <!-- COIDEA:main:section:headline:title START -->
              <h1 class="title">
                {{ category.slug }}.
              </h1>
              <!-- COIDEA:main:section:headline:title END -->

              <!-- COIDEA:main:section:headline:subtitle START -->
              <h2 class="subtitle" v-html="category.description"></h2>
              <!-- COIDEA:main:section:headline:subtitle END -->

            </div>
          </div>
        </div>
      </section>
      <!-- COIDEA:main:section:headline END -->

      <!-- COIDEA:main:main START -->
      <div class="main">
        <!-- COIDEA:main:section:grid START -->
        <section class="grid">
          <div class="container">
            <div class="row">
              
              <!-- COIDEA:main:section:grid:item START -->
              <article v-for="(item, index) in items" :key="item.id" v-if="items && items.length > 0 && item.category == catSlug && index <= limitationList">
                <div class="image">
                  <nuxt-link :to="'/single/' + item.slug" title="Triple Panel Reveal Slideshow">
                    <img :src="item.image" :alt="'COIDEA - Grid - ' + item.headline" />
                  </nuxt-link>
                </div>        
                <div class="date">
                  <div>
                    <p>In <nuxt-link :to="'/categories/' + item.category" :title="item.category">{{ item.category }}</nuxt-link> by <nuxt-link to="/about" :title="item.author">{{ item.author }}</nuxt-link> on {{ item.date }}</p>
                  </div>
                </div>      
                <div class="headline">
                  <nuxt-link :to="'/single/' + item.slug" :title="item.headline">
                    <h3>
                      {{ item.headline }}
                    </h3>
                  </nuxt-link>
                </div>
              </article>
              <!-- COIDEA:main:section:grid:item END -->

              <div class="view-all">
                <!-- <nuxt-link to="/" title="VIEW ALL">LOAD MORE</nuxt-link> -->
                <button class="load-more" @click="updateLimitation(limitationList)">
                  {{ limitationList >= items.length ? 'RESET' : 'LOAD MORE' }}
                </button>
                <!-- <p>or check categories</p> -->
              </div>

            </div>
          </div>
        </section>
        <!-- COIDEA:main:section:grid END --> 

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
              <div class="card" v-for="(category, index) in categories" :key="index" v-if="category.slug != catSlug">
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
        catSlug: this.$route.params.slug,
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
        limitationList: 4
      }
    },
    methods: {
      updateLimitation(limitationList){
        if ( this.limitationList >= this.items.length) {
          this.limitationList = 4;
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
                width: 23%;
                width: calc( 25% - 32px );
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
        &.grid {
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
                width: 40%;
                width: calc( 50% - 32px );
                height: auto;
                overflow: hidden;
                margin: 0; padding: 0 16px 16px;
                float: left;
                @include maxquery( 992px ) {
                  width: 90%;
                  width: calc( 100% - 32px );
                }
                .image {
                  @include position--default();
                  width: 100%;
                  height: auto;
                  overflow: hidden;
                  transition: all .45s ease-in-out;
                  -webkit-transition: all .45s ease-in-out;
                  a {
                    position: relative;
                    z-index: 5;
                    img {
                      @include position--default();
                      width: 100%;
                      min-width: 100%;
                      max-width: 100%;
                      height: auto;
                    }
                  }
                  &:hover {
                    opacity: 0.7;
                  }
                }
                .date {
                  @include position--default();
                  width: 100%;
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
                    max-width: 480px;
                    height: 10px;
                    bottom: 20px; left: 0;
                    z-index: 0;
                    opacity: .3;
                  }
                }
                .headline {
                  @include position--default();
                  width: 100%;
                  height: auto;
                  overflow: hidden;
                  a {
                    @include position--default();
                    width: 100%;
                    height: auto;  
                    color: inherit;
                    font-weight: 700;
                    text-decoration: none;
                    overflow: hidden;
                    transition: all .45s ease-in-out;
                    -webkit-transition: all .45s ease-in-out;
                    h3 {
                      max-width: 480px;
                      min-height: 120px;
                      margin: 0; padding: 0 16px;
                      font-size: 48px;
                      line-height: 60px;
                      font-weight: bold;
                      @include maxquery( 1240px ) {
                        max-width: 280px;
                        font-size: 28px;
                        line-height: 38px;
                      }
                    }
                    &:hover {
                      &:hover {
                        color: $blue;
                      }
                    }
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
                  width: 100%;
                  height: 128px;
                  color: $white;
                  font-size: 32px;
                  line-height: 128px;
                  font-weight: 200;
                  text-align: center;
                  text-decoration: none;
                  cursor: pointer;
                  outline: 0px none;
                  outline: 0px;
                  transition: all .45s ease-in-out;
                  -webkit-transition: all .45s ease-in-out;
                  box-shadow: 0 7px 13px rgba(0,0,0,0.02), 0 7px 12px rgba(0,0,0,0.025);
                  &:hover {
                    background-color: $darkblue;
                    box-shadow: 0 24px 36px rgba(0,0,0,0.045), 0 10px 10px rgba(0,0,0,0.042);
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

