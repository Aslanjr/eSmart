<template>
  <div class="home">
    <Header class="header" />
    <div class="content">
        <Sarah/>
    </div>
  </div>
</template>

<script>

import Header from "../components/header.vue"
import Sarah  from '../components/Content/Sarah'

export default {
  name: 'Home',
  components: {
    Header,
    Sarah
  }
}
</script>
<style lang="scss">
    .header{
      position: relative;
      z-index: 2;
    }
    .content{
      position: absolute;
      height: 100vh;
      overflow: hidden;
      z-index: 1;
      top: 0;
      left: 0;
      width: 100%;
    }
</style>
