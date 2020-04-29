<template>
  <div id="app">
    <div id="nav">
      <NavBar />
    </div>
    <b-container>
      <router-view/>
    </b-container>
  </div>
</template>

<script>
  import NavBar from "@/components/NavBar";
  export default {
    components: {
      NavBar
    }
  }
</script>
<style lang="scss">
</style>
