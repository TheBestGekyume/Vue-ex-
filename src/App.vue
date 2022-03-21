<template>
  <div>
    <NavbarComponents />
    <PoemaFormComponent />
  </div>
</template>

<script>
import NavbarComponents from './components/NavBar.vue';
import PoemaFormComponent from './components/poema/PoemaForm.vue';

export default {
  name: 'App',
  components: {
    NavbarComponents,
    PoemaFormComponent
  },
};
</script>

<style>

</style>

