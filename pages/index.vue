<template>
  <PatronizeAuthLayout>
    <div>
      <button>Login</button>
      <div>
        <div>
          <a href="#" @click="changeTab('verify')">Verify Account</a>
          <a href="#" @click="changeTab('social')">Social Handles</a>
          <a href="#" @click="changeTab('business')">Business Categories</a>
        </div>
        <div class="divider" />
      </div>
      <div>
        <div v-if="tab == 'verify'">
<verify-account/>
        </div>
          <div v-if="tab == 'social'">
<social-handles/>
        </div>
          <div v-if="tab == 'business'">
<business-category/>
        </div>
      </div>
    </div>
    <!-- <h2 class="auth-page__title text-left mb-2 text-2xl">
        Welcome Back
      </h2>
        <p>
          Forgot your password? <nuxt-link to="/auth/password/reset" class="primary">
            Reset it
          </nuxt-link>
        <p>
          Don't have an account yet? <nuxt-link to="/auth/signup" class="primary">
            Create one
          </nuxt-link>
        </p> -->
  </PatronizeAuthLayout>
</template>

<script>
import PatronizeAuthLayout from "~/components/layout/PatronizeAuthLayout";
import BusinessCategory from '../components/tabs/BusinessCategory.vue';
import SocialHandles from '../components/tabs/SocialHandles.vue';
import VerifyAccount from '../components/tabs/VerifyAccount.vue';

export default {
  components: {
    PatronizeAuthLayout,
    SocialHandles,
    VerifyAccount,
    BusinessCategory,
  },
  data() {
    return {
      tab: 'verify'
    }
  },
  methods:{
    changeTab(tab){
      this.tab = tab
    }
  }
};
</script>

<style lang="scss" scoped>
$grey-dark: #979797;
$grey: #666666;
$grey-grey-dark: #484747;
$grey-light: #c4c4c4;
$grey-light-divide: #f5f5f5;
$grey-border: #eaecee;
$grey-border-bottom: #d8d8d8;
.divider {
  padding: 0;
  width: 100%;
  border-bottom: 1px solid #e9eef4;

  &__bg-grey-light {
    border-color: #c4c4c4;
  }

  &__bg-grey-light-divide {
    border-color: $grey-light-divide;
  }
}
</style>