<template>
  <div id="app">
    <Inputdata v-on:taketoapp="getData"/>
    <Inputdatatable v-on:delTable="deleteTable" v-bind:getarray="studentArray"/>

   
  </div>
</template>

<script>
import Inputdata from './components/inputdata.vue';
import Inputdatatable from './components/inputdatatable.vue';

export default {
  name: 'App',

  components: {
    Inputdata,
    Inputdatatable
  },

  data() {
    return {
      studentArray: []
    }
  },

  methods: {
    getData(name, school, dept) {
      let studObj = {stuname: name, stuschool: school, studept: dept}
      let {studentArray} = this;
      this.studentArray = [...studentArray, studObj];
    },

    deleteTable (index) {
      this.studentArray.splice(index, 1);
    }
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
