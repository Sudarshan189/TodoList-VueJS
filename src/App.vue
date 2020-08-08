<template>
  <div id="app">
    <div id="nav">
      <Header/>
    </div>
    <router-view/>
  </div>
</template>

<script>
import Header from './components/layout/Header'
export default {
  name:'app',
  components: {
    Header
  }
}
</script>

<style scope>

</style>
