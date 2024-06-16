<template>
  <div id="app">
     <div class="d-flex justify-content-center">
      <checkBoxDesign/>
    </div>
  </div>
</template>

<script>
import checkBoxDesign from './components/checkboxDesign.vue'

export default {
  name: 'App',
  components: {
    checkBoxDesign
  }
}
</script>

<style>
#app {
  font-family: Montserrat;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #1F2128;
  margin-top: 60px;
}

</style>
