<template>

  <footer>
    <div class="container">
      <div class="row">
        <div class="footer">
          
          <div class="footer-left">
            <!-- COIDEA:footer:logo START -->
            <div class="logo">
              <nuxt-link to="/" title="COIDEA">
                <span>
                  <img width="150" height="32" src="~/assets/images/design/coidea-logo-footer.png" alt="COIDEA - Logo - Footer" />
                </span>
              </nuxt-link>
            </div>
            <!-- COIDEA:footer:logo END -->

            <!-- COIDEA:footer:navigation:categories START -->
            <nav>
              <ul>
                <li><nuxt-link to="/categories/brainstorms" title="brainstorms">brainstorms.</nuxt-link></li>
                <li><nuxt-link to="/categories/tutorials" title="tutorials">tutorials.</nuxt-link></li>
                <li><nuxt-link to="/categories/abstract" title="abstract">abstract.</nuxt-link></li>
                <li><nuxt-link to="/categories/resources" title="resources">resources.</nuxt-link></li>
                <li><nuxt-link to="/categories/gifts" title="gifts">gifts.</nuxt-link></li>
              </ul>
            </nav>
            <!-- COIDEA:header:navigation:categories END -->

            <!-- COIDEA:footer:navigation:categories START -->
            <nav>
              <ul>
                <li><nuxt-link to="/about" title="about">about.</nuxt-link></li>
                <li><nuxt-link to="/contact" title="contact">contact.</nuxt-link></li>
                <li><nuxt-link to="/categories" title="archives">archives.</nuxt-link></li>
              </ul>
            </nav>
            <!-- COIDEA:header:navigation:categories END -->
          </div>

          <div class="footer-right">
            <p>COIDEA is a web design and development blog, which we hope will bring together all the development and design enthusiasts.</p>
            <p>© <strong>COIDEA</strong> 2018 by <a href="https://coidea.website/about" target="_blank">Mirza Hodzic</a> / <a href="https://coidea.website" target="_blank">COIDEA</a></p>
          </div>

        </div>
      </div>
    </div>
  </footer>

</template>


<script>

</script>



<style lang="scss" scoped>

  @import '~/assets/scss/styles.scss';

  footer {
    @include position--default();
    background-color: $darkblue;
    width: 100%;
    height: auto;
    overflow: hidden;
    padding: 78px 0;
    .container {
      @include position--default();
      width: 100%;
      height: auto;
      overflow: hidden;
      margin: 0 auto;
      .row {
        padding: 0 .75em;
        .footer {
          padding: 0 16px;
          /*
          @include maxquery( 992px ) {
            padding: 0 .75em;
          }
          */
          .footer-left {
            @include position--default();
            width: 50%;
            float: left;
            @include maxquery( 992px ) {
              width: 100%;
            }
            // footer -> logo
            .logo {
              @include position--default();
              width: 150px;
              height: auto;
              float: left;
              margin-bottom: 4px;
              /*
              @include maxquery( 640px ) {
                width: 171px;
              }
              */
              a {
                span {
                  position: relative;
                  img {
                    position: relative;
                    padding-top: 5px;
                    z-index: 1;
                    /*
                    @include maxquery( 640px ) {
                      width: 171px;
                      height: auto;
                    }
                    */
                  }
                  &::after {
                    background-color: $blue;
                    @include pseudo--ba();
                    width: 100%;
                    width: calc(100% - 54px);
                    height: 16px;
                    bottom: 0px; right: 2px;
                    z-index: 0;
                    transition: all .25s ease-in-out;
                    -webkit-transition: all .25s ease-in-out;
                  }
                }
                &:hover {
                  span {
                    &::after {
                      height: 42px;
                    }
                  }
                }
                &.nuxt-link-active {
                  color: $blue;
                  font-weight: 700;
                }
              }
            }
            nav {
              @include position--default();
              width: 100%;
              height: auto;
              ul {
                @include position--default();
                width: 100%;
                height: auto;
                float: right;
                margin: 0; padding: 0;
                list-style-type: none;
                li {
                  @include position--default(inline-block, relative);
                  padding-right: 16px;
                  a {
                    font-size: 14px;
                    line-height: 22px;
                    color: $white;
                    font-weight: 200;
                    text-decoration: none;
                    transition: all .45s ease-in-out;
                    -webkit-transition: all .45s ease-in-out;
                    &:hover {
                      color: $blue;
                    }
                    &.not-yet-available {
                      position: relative;
                      pointer-events: none;
                      cursor: default;
                      &::after {
                        background-color: $blue;
                        @include pseudo--ba();
                        width: 100%;
                        height: 2px;
                        top: 50%;
                        right: 0;
                        left: 0;
                        opacity: .85;
                      }
                    }
                  }
                }
              }
            }
          }
          .footer-right {
            @include position--default();
            width: 276px;
            float: right;
            @include maxquery( 992px ) {
              width: 100%;
              padding-top: 48px;
            }
            p {
              max-width: 448px;
              font-size: 14px;
              line-height: 22px;
              color: $white;
              font-weight: 200;
              text-align: right;
              float: right;
              clear: both;
              @include maxquery( 992px ) {
                text-align: left;
                float: left;
              }
              a {
                color: $white;
                font-weight: bold;
                text-decoration: none;
                transition: all .45s ease-in-out;
                -webkit-transition: all .45s ease-in-out;
                &:hover {
                  color: $blue;
                }
              }
            }
          }
        }
      }
    }
  }

</style>

