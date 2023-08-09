<template>
  <NavBar/>
  <div class="bg-light position-relative collapsed main-content" style="min-height: calc(100vh - 75px) !important;">
    <div class="p-0 pb-5 container-fluid">
      <div class="mx-auto container-fluid">
        <div class="row mt-2 no-gutters">
          <div class="px-0 col-12">
            <OfertasEmpleo/>
          </div>
        </div>
      </div>
    </div>
  </div>  


</template>

<script lang="ts" setup>
import 'bootstrap/dist/css/bootstrap.css'
import NavBar from './components/NavBar.vue'
import OfertasEmpleo from './components/OfertasEmpleo.vue';
</script>

<style>

</style>
