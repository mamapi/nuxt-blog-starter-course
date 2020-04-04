<template>
  <b-navbar type="is-primary" spaced>
    <template slot="brand">
      <b-navbar-item tag="nuxt-link" :to="{ name: 'index' }" class="logo-link">
        <img :src="require('~/assets/logo.png')" alt="" class="logo" />
      </b-navbar-item>
    </template>
    <template slot="start">
      <b-navbar-item tag="nuxt-link" :to="{ name: 'index' }">
        Artykuły
      </b-navbar-item>
      <b-navbar-item href="#">
        O nas
      </b-navbar-item>
      <b-navbar-item href="#">
        Kontakt
      </b-navbar-item>
    </template>
  </b-navbar>
</template>
<style lang="scss" scoped>
.logo-link {
  padding: 5px;
  margin-right: 20px;
}
.logo {
  height: 40px;
  max-height: 100%;
}
</style>
