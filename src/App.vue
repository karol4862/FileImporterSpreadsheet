<template>
  <div id="app">
    <CsvImport v-model="val"  :labels="['name', 'surname']" :separators="[',']" />
  </div>
</template>

<script>
import CsvImport from './components/CsvImport.vue';

export default {
  name: 'App',
  data() {
    return {
      val: '',
    };
  },
  components: {
    CsvImport,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
