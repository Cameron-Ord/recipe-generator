<script setup>
import PageHeader from './components/PageHeader.vue';
import PageFooter from './components/PageFooter.vue';
</script>

<template>
  <header class="pageHeader">
    <page-header></page-header>
  </header>
  <RouterView />
  <footer class="pageFooter">
    <page-footer></page-footer>
  </footer>
</template>

<style scoped>
.pageHeader{
  display: grid;
  min-height: 100px;
  align-items: center;
}
.pageFooter{
  display: grid;
  min-height: 100px;
  align-items: center;
}
</style>
