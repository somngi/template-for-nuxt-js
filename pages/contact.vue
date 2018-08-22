<template>
  <div>

  <app-header/>

  <main>
    
    <!-- COIDEA:main:section:headline START -->
    <section class="headline">
      <div class="container">
        <div class="row">
          <div class="title-subtitle">
          
            <!-- COIDEA:main:section:headline:title START -->
            <h1 class="title">Contact us</h1>
            <!-- COIDEA:main:section:headline:title END -->

            <!-- COIDEA:main:section:headline:subtitle START -->
            <h2 class="subtitle">If you’d like to write for us, advertise with us or just say hello, click the button below, send e-mail and we’ll get back to you as soon as possible.</h2>
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
              
              <div class="content">

                <div>
                  <p><strong>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat.</strong></p>
                </div>

                <div>
                  <p><strong>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat.</strong>. </p>
                </div>

                <div>
                  <p><strong>Lorem ipsum dolor sit amet, consetetur sadipscing elitr.</strong></p>
                </div>
                
              </div>

              <div class="content">

                <div>
                  <p>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.</p>
                </div>

              </div>

            </article>

            <div class="view-all">
              <a href="mailto:hello@coidea.website" class="load-more" title="CONTACT">CONTACT</a>
            </div>

          </div>
        </div>
      </section>
      <!-- COIDEA:main:section:article END -->

      <!-- COIDEA:main:main START -->
      <app-sidebar />
      <!-- COIDEA:main:main END -->

    </div>
    <!-- COIDEA:main:main START --> 


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

  <!-- COIDEA:footer START -->
  <app-footer/>
  <!-- COIDEA:footer END -->

  </div>
</template>


<script>
import AppHeader from '~/components/AppHeader.vue'
import AppFooter from '~/components/AppFooter.vue'
import AppSidebar from '~/components/AppSidebar.vue'

// temp images categories
import icon1 from '~/assets/images/design/icon-tutorials.png'
import icon2 from '~/assets/images/design/icon-playground.png'
import icon3 from '~/assets/images/design/icon-blueprint.png'
import icon4 from '~/assets/images/design/icon-inspiration.png'
import icon5 from '~/assets/images/design/icon-freebies.png'

export default {
  data() {
    return {
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
                .content {
                  @include position--default();
                  width: 48%;
                  max-width: 496px;
                  width: calc( 50% - 32px );
                  height: auto;
                  overflow: hidden;
                  margin-bottom: 16px;
                  float: left;
                  @include maxquery( 992px ) {
                    width: calc( 100% - 32px );
                  }
                  div {
                    @include position--default();
                    width: 90%;
                    width: calc( 100% - 32px );
                    height: auto;
                    overflow: hidden;
                    padding-bottom: 32px;
                    @include maxquery( 992px ) {
                      width: 100%;
                    }
                    h3 {
                      margin: 0;
                    }
                    p {
                      padding: 0; padding-top: 16px;
                      margin: 0;
                      strong {
                        font-weight: 700;
                      }
                    }
                    a {
                      color: $blue;
                      text-decoration: none;
                      transition: all .45s ease-in-out;
                      -webkit-transition: all .45s ease-in-out;
                      &:hover {
                        color: inherit;
                      }
                    }
                    &.author {
                      p {
                        font-weight: 700;
                      }
                      a {
                        color: $blue;
                        text-decoration: none;
                        transition: all .45s ease-in-out;
                        -webkit-transition: all .45s ease-in-out;
                        &:hover {
                          color: inherit;
                        }
                      }
                    }
                    &.mirza-hodzic {
                      padding: 16px;
                      background-color: $blue;
                      color: $white;
                      @include maxquery( 992px ) {
                        width: calc( 100% - 32px );
                      }
                      img {
                        width: 100%;
                        max-width: 124px;
                        border: 1px solid white;
                        float: left;
                        margin-top: 22px;
                        margin-right: 16px;
                      }
                      a {
                        color: $white;
                        font-weight: bold;
                        margin-right: 16px;
                      }
                      p {
                        &.right {
                          float: right;
                        }
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
                  float: left;
                  cursor: pointer;
                  outline: 0px none;
                  outline: 0px;
                  transition: all .45s ease-in-out;
                  -webkit-transition: all .45s ease-in-out;
                  box-shadow: 0 7px 13px rgba(0,0,0,0.02), 0 7px 12px rgba(0,0,0,0.025);
                  @include maxquery( 992px ) {
                    margin: 0 0 32px 0;
                  }
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

