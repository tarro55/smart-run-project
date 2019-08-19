<template>
  <q-page class="flex flex-center">
    <h2>HELLO WORLD</h2>
    <img alt="Quasar logo" src="~assets/quasar-logo-full.svg">
    
    <bluetooth/>
  </q-page>
</template>

<style>
</style>

<script>
import bluetooth from "../components/Bluetooth"
export default {
  name: 'PageIndex',
  components:{
    
    bluetooth,
  }
}
</script>
