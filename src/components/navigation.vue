
<template>
  <div>
    <header class="bg-white black-80 tc pt4 avenir">
      <h1 class="mt2 mb0 baskerville i fw1 f1 mh2">Art Gallery</h1>

      <nav class="bt bb tc mw7 center mt4 flex justify-between flex-wrap">
        <a class="f6 f5-l link bg-animate black-80 hover-bg-washed-red dib pv3 ph2 ph4-l" href="/">Home</a>

        <a class="f6 f5-l link bg-animate black-80 hover-lightest-blue dib pv3 ph2 ph4-l" v-if="$auth.isAuthenticated" href="">
          <router-link class="link black" to="/gallery">Gallery</router-link>
        </a>

        <a class="f6 f5-l link bg-animate black-80 hover-bg-light-yellow dib pv3 ph2 ph4-l pointer"  v-if="$auth.isAuthenticated">
          <router-link class="link black" to="/profile">Profile</router-link>
        </a>

        <a class="f6 f5-l link bg-animate black-80 hover-bg-light-pink dib pv3 ph2 ph4-l pointer" v-if="!$auth.isAuthenticated && !$auth.loading">
          <span @click.prevent="login"><i class="fas fa-sign-in-alt mr2"></i>Login</span>
        </a>
             
        <a class="f6 f5-l link bg-animate black-80 hover-bg-light-green dib pv3 ph2 ph4-l pointer" v-if="$auth.isAuthenticated">
          <span href="#" @click.prevent="logout"> Log out </span>
        </a>
      </nav>
    </header>
  </div>
</template>
<script>
export default {
  name: 'navigation',

  methods: {
    login() {
      this.$auth.loginWithRedirect();
    },
    logout() {
      this.$auth.logout();
      this.$router.push({ path: "/" });
    }
  }
}
</script>
