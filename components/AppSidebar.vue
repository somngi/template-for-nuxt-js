<template>
  <div class="sidebar">
    <div class="sidebar-inner">
      <div class="header">
        <p><span>Advertisement</span> <!-- <nuxt-link to="/"><i class="material-icons">info_outline</i></nuxt-link> --></p>
      </div>
      <div class="big-ad">
        <a href="https://github.com/COIDEAwebsite" target="_blank">
          <img src="~/assets/images/temp/github-ad.jpg" />
        </a>
      </div>
    </div>
  </div>
</template>


<script>

</script>


<style lang="scss" scoped>

  @import '~/assets/scss/styles.scss';

  main {
    .main {
      .sidebar {
        background-color: $white;
        @include position--default();
        width: 316px;
        height: auto;
        min-height: 280px;
        float: left;
        margin-top: 82px;
        margin-right: 32px;
        border: 2px solid $lightblue;
        @include maxquery( 768px ) {
          width: 100%;
        }
        .sidebar-inner {
          @include position--default();
          padding: 0 8px;
          @include maxquery( 768px ) {
            text-align: center;
          }
          .header {
            p {
              color: $darkblue;
              font-size: 14px;
              line-height: 14px;
              font-weight: 200;
            }
            a {
              color: $darkblue;
              font-size: 14px;
              line-height: 22px;
              font-weight: 700;
              text-decoration: none;
              i {
                color: $darkblue;
                font-size: 14px;
                line-height: 14px;
              }
            }
          }
          .big-ad {
            @include position--default();
            width: 300px;
            height: auto;
            img {
              @include position--default();
              width: 100%;
              min-width: 100%;
              max-width: 100%;
              height: auto;
            }
            @include maxquery( 768px ) {
              margin: 16px auto;
            }
          }
        }
        &::after {
          background-color: $white;
          @include pseudo--ba();
          width: 100%;
          height: 6000px;
          top: 100%; right: 0; left: -2px;
          border-right: 2px solid $lightblue;
          border-left: 2px solid $lightblue;
        }
      }
    }
  }

</style>
