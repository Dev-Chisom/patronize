<template>
  <div class="onboarding-layout">
    <div>
      <OfflineNotice v-if="$nuxt.isOffline" />
    </div>
    <div class="page-container">
      <div class="side-content">
        <div class="side-content__bg" />
        <div class="page-content">
         
            <div class="image-container" style="margin: -1.5rem">
                <img
                  src="~/assets/img/svg/onboarding.png"
                  alt="patronize"
                  class="side-content-image"
                   style="margin-top: 35rem"
                />
            </div>
          </div>
      </div>
      <div class="main-content">
        <div class="page-content">
          <slot />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import OfflineNotice from "~/components/utilities/OfflineNotice";

export default {
  components: {
    OfflineNotice,
  },
//   data(){
//        return {
//       showTransition: false,
//     };
//   },
//     mounted () {
//     this.showTransition = true;
//   },
};
</script>

<style lang="scss">
.onboarding-layout {
  transition: background-color 0.3s ease-in-out;

  .stick {
    position: sticky;
    top: 0;
    z-index: 999;
  }

  .page-container {
    position: relative;
    display: flex;

    .side-content {
      position: relative;
      display: none;
      background-color: #0262d2;
      color: #fff;
      max-width: 30%;

      @media (min-width: 1024px) {
        width: 100%;
        min-height: 100vh;
        display: flex;
        flex-direction: column;
      }

      .side-content__bg {
        width: 100%;
        min-height: 100%;
        position: absolute;
        top: 0;
        left: 0;
        opacity: 0.05;
        background-image: #0262d2;
        background-repeat: no-repeat;
        background-size: cover;
      }
      .side-content-image {
        transition: opacity 0.6s ease-in-out, transform 0.6s ease-in-out;
      }
    }

    .main-content {
      width: 100%;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    .page-content {
      display: flex;
      flex-direction: column;
      z-index: 10;
      padding: 1.5rem;
      margin-top: 3.5rem;
      min-height: calc(100vh - 3.5rem);

    //   .image-container {
    //     margin-top: 1rem;
    //     position: sticky;
    //     bottom: 0;
    //   }
      
      .side-content-image {
        transition: opacity 0.6s ease-in-out, transform 0.6s ease-in-out;
        width: 100%;
        margin-top: 1rem;
        position: sticky;
        bottom: -100;
      }
    }
  }
}
</style>
