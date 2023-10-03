<template>
  <div id="app">
    <AppHeader />
    <div class="container mx-auto">
      <AppSlider />
    </div>
  </div>
</template>

<script>
  import AppHeader from './components/AppHeader.vue';
  import AppSlider from './components/AppSlider.vue';

  export default {
    components: {
      AppHeader,
      AppSlider,
    },
  };
</script>
