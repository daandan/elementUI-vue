<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
  .router-fade-enter-active,
  .router-fade-leave-active{
    transition:opacity .3s;
  }
  .router-fade-enter,
  .router-fade-leave-active{
    opacity: 0;
  }
  .router-slide-enter,
  .router-slide-leave-active{
    transform: translate3d(2rem,0,0);
    opacity: 0;
  }
  .component-fade-enter-active,
  .component-fade-leave-active{
    transition:opacity .3s ease;
  }
  .component-fade-enter,
  .component-fade-leave-to{
    opacity: 0;
  }
</style>
