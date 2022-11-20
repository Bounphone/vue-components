<template>
  <form action="" @submit.prevent="submitForm">
    <div class="form-control">
      <label for="emp-name">Employee's name: </label>
      <input type="text" v-model.trim="employee.name" />
    </div>
    <div class="form-control">
      <label for="emp-salary">Employee's salary: </label>
      <input type="number" v-model="employee.salary" />
    </div>
    <div class="form-control">
      <label for="emp-department">Employee's department: </label>
      <select name="" id="" v-model="employee.department">
        <option value="Marketing">Marketing</option>
        <option value="Sale">Sale</option>
        <option value="Accounting">Accounting</option>
      </select>
    </div>
    <div class="form-control">
      <label for="emp-gender">Employee's gender: </label>
      <div>
        <input type="radio" value="Male" v-model="employee.gender">
        <label for="gender-name">Male</label>
      </div>
      <div>
        <input type="radio" value="Female" v-model="employee.gender">
        <label for="gender-name">Female</label>
      </div>
    </div>
    <div class="form-control">
      <label for="emp-language">Employee's language: </label>
      <div>
        <input type="checkbox" value="English" v-model="employee.language">
        <label for="gender-name">English</label>
      </div>
      <div>
        <input type="checkbox" value="Lao" v-model="employee.language">
        <label for="gender-name">Lao</label>
      </div>
      <div>
        <input type="checkbox" value="Chinese" v-model="employee.language">
        <label for="gender-name">Chinese</label>
      </div>
    </div>
    <div>
      <button>Save data</button>
    </div>
  </form>
</template>

<script>
export default {
  name: "FormComponents",
  data() {
    return {
      employee: {
        name: "",
        salary: 15000,
        department : "Marketing",
        gender : "Male",
        language : []
      },
    };
  },
  methods : {
    submitForm(){
        const newEmp = {
            name : this.employee.name,
            salary : this.employee.salary,
            department : this.employee.department,
            gender : this.employee.gender,
            language : this.employee.language,
        }
        this.$emit("save", newEmp)
        this.resetForm()
    },
    resetForm(){
        this.employee = {
        name: "",
        salary: 15000,
        department : "Marketing",
        gender : "Male",
        language : []
      };
    }
  }
};
</script>

<style scoped>
form{
    margin: 2rem auto;
    max-width: 40rem;
    border-radius: 12px;
    box-shadow:0 4px 4px rgba(0, 0, 0, 0.25);
    padding: 2rem;
    background: white;
}
.form-control{
    margin: 0.5rem 0;
}
label {
    font-weight: bold;
}
input, select{
    display: block;
    width: 100%;
    margin-top: 0.5rem;
}
button {
    background: purple;
    color: white;
    cursor: pointer;
    padding: 5px 40px;
}
input[type = "radio"], input[type = "checkbox"]{
    display: inline-block;
    width: auto;
    margin: 1rem;
    
}
input[type = "radio"] + label, input[type = "checkbox"] + label{
    font-weight: normal;
}
</style>
