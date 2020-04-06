<template>
  <div id="app">
    <Resume/>
  </div>
</template>

<script>
import resume from './components'

export default {
  name: 'App',
  components: {
    Resume : resume
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
}
</style>
