<template>
  <div id="app">

    <div class="nav has-shadow">
      <div class="container">
        <div class="navbar-start">
          <a class="nav-item">MyCompany</a>
        </div>

        <span class="nav-toggel">
          <span></span>
          <span></span>
          <span></span>
        </span>

        <div class="navbar-end nav-menu">
        <div class="nav-item">
          <router-link to="/" class="nav item r-item">Home</router-link>
          <router-link to="faq" class="nav item r-item">Features</router-link>
          <router-link to="faq" class="nav item r-item">About</router-link>
          <router-link to="faq" class="nav item r-item">FAQ</router-link>
        </div>
          <div class="nav-item">
            <p class="control">
              <a class="button is-primary is-outlined">
                <span class="icon">
                  <i class="fa fa-download"></i>
                </span>
                <span>Join Now</span>
              </a>
            </p>
          </div>

        </div>
      </div>
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style lang="sass">
@import '../node_modules/bulma/bulma.sass'
@import 'mq'

</style>
