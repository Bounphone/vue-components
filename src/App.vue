<template>
  <header>
    <h1>Management system</h1>
  </header>
  <FormComponentsVue @save="insertEmp"></FormComponentsVue>
  <section class="employee-content" v-if="employees.length > 0">
    <h2>Employee data</h2>
    <ListData :employees="employees"/>
  </section>
</template>

<script>
import FormComponentsVue from './components/FormComponents.vue';
import ListData from "./components/ListData.vue";
export default {
  name: "App",
  components: {
    ListData,
    FormComponentsVue
  },
  data(){
    return {
      employees : []
    }
  },
  methods : {
    insertEmp(emp){
      this.employees.push(emp)
    }
  }
};
</script>
<style>
*{
  box-sizing: border-box;
}
body{
  margin: 0;
}
header{
  box-shadow: 0 2px 8px rgba(0, 0, 0, 26);
  margin: 3rem;
  border-radius: 10px;
  padding: 1rem;
  background-color: purple;
  color: white;
  text-align: center;
}
.employee-content{
  box-shadow: 0 2px 8px rgba(0, 0, 0, 26);
  margin: 3rem;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
}
.employee-content h2{
  font-size: 2rem;
  border-bottom: 4px solid grey;
  color: purple;
  margin: 0 0 1rem 0;
}
</style>