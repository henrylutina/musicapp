<template>
  <div id="app">
    <app-header/>
    <router-view/>
    <app-footer/>
  </div>
</template>

<script>
import header from './components/Views/header'
import footer from './components/Views/footer'

export default {
  name: 'App',
  components: {
    'app-header': header,
    'app-footer': footer
  }
}
</script>

<style>

</style>
