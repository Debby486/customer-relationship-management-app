<template>
  <Navbar />

  <section class="section">
    <router-view/>
  </section>
</template>

<script>
  import Navbar from '@/components/layout/Navbar'
  export default {
    name: 'App',
    components: {
      Navbar
    }
  }
</script>

<style lang="scss">
@import '../node_modules/bulma';
</style>
