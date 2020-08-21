<template>
  <div id="app">
    <Activity /> 
    <Cards />
    <FooterPage/>  
  </div>

</template>

<script>

import Activity from './components/Activity';
import Cards from './components/Cards';
import FooterPage from './components/FooterPage';

export default { 
  name: 'App',
  components: {
    Activity,
    Cards,
    FooterPage   
  }
}
</script>

<style>

</style>
