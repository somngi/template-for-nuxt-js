<template>

  <header>
    <div class="container">
      <div class="row">
        <div class="header">
        
          <!-- COIDEA:header:logo START -->
          <div class="logo">
            <nuxt-link to="/" title="COIDEA">
              <span>
                <img width="150" height="32" src="~/assets/images/design/coidea-logo.png" alt="COIDEA - Logo" />
              </span>
            </nuxt-link>
          </div>
          <!-- COIDEA:header:logo END -->

          <!-- COIDEA:header:navigation:social START -->
          <nav class="social">
            <ul>
              <li><a href="https://github.com/COIDEAwebsite" target="_blank" title="GITHUB">G</a></li>
              <li><a href="https://www.instagram.com/coidea.website/" target="_blank" title="INSTAGRAM">I</a></li>
              <li><a href="https://twitter.com/CoideaW" target="_blank" title="TWITTER">T</a></li>
            </ul>
          </nav>
          <!-- COIDEA:header:navigation:social END -->

        </div>
      </div>
    </div>
  </header>

</template>


<script>

</script>



<style lang="scss" scoped>

  @import '~/assets/scss/styles.scss';

  header {
    @include position--default();
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
        .header {
          padding: 0 16px;
          /*
          @include maxquery( 992px ) {
            padding: 0 .75em;
          }
          */
          // header -> logo
          .logo {
            @include position--default();
            width: 150px;
            height: auto;
            float: left;
            /*
            @include maxquery( 640px ) {
              width: 171px;
            }
            */
            a {
              span {
                position: relative;
                img {
                  padding-top: 5px;
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
                  z-index: -1;
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
            }
          }
          // header -> navigation ( social )
          nav {
            @include position--default();
            width: 140px;
            height: auto;
            float: right;
            margin-top: 9px;
            @include maxquery( 768px ) {
              float: left;
              overflow: hidden;
              clear: both;
              margin-left: -.75em;
              margin-top: 1.5em;
            }
            ul {
              @include position--default();
              width: 100%;
              height: auto;
              float: right;
              margin: 0; padding: 0;
              list-style-type: none;
              li {
                @include position--default();
                width: 32px;
                height: 32px;
                float: left;
                margin-left: .75em;
                a {
                  @include position--default();
                  background-color: $blue;
                  color: $white !important;
                  width: 32px;
                  height: 32px;
                  font-size: 24px;
                  font-weight: 700;
                  line-height: 32px;
                  text-align: center;
                  text-decoration: none;
                  transition: all .45s ease-in-out;
                  -webkit-transition: all .45s ease-in-out;
                  &:hover {
                    background-color: $darkblue !important;
                    box-shadow: 0 3px 9px rgba(0,0,0,0.045), 0 3px 3px rgba(0,0,0,0.042);
                  }
                }
                /*
                &:last-child {
                  width: 80px;
                  a {
                    width: 80px;
                  }
                }
                */
              }
            }
          }
        }
      }
    }
  }

</style>

