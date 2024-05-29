<template>
  <!-- Container utama aplikasi -->
  <div id="app">
    <!-- Memanggil ParentComponent -->
    <ParentComponent />
  </div>
</template>

<script>
import ParentComponent from './components/ParentComponent.vue';

export default {
  components: {
    ParentComponent,
  },
};
</script>