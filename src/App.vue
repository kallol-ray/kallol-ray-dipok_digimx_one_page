<template>
  <div id="app">
    <navbar></navbar>
    <!-- <router-view/> -->
    <master></master>
    <my-footer></my-footer>
  </div>
</template>

<script>
import Navbar from './components/includes/Navbar.vue'
import Footer from './components/includes/Footer.vue'
import Master from './components/master/Master.vue'
export default {
  name: 'App',
  components: {
    'navbar': Navbar,
    'master': Master,
    'my-footer': Footer
  }
}
</script>

<style>

</style>
