<template>
  <div>
    <div class="loading" v-if="loading">
      Loading
    </div>
    <div class="employees" v-else>
      <Employee
        v-for="employee in employees" 
        :key="employee.id"
        :employee="employee"
      />
    </div>
  </div>
</template>

<script>
import Employee from './Employee.vue'

export default {
  name: 'Employees',
  components: {
    Employee
  },
  data() {
    return {
      employees: [],
      loading: true,
    }
  },
  beforeMount(){
    this.fetchEmployees();
  },
  methods: {
    async fetchEmployees(){
      this.loading = true;
      const res = await fetch('https://my.api.mockaroo.com/employee.json?key=53b1b110');
      const data = await res.json();
      this.employees = data;
      this.loading = false;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.employees {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  margin-bottom: 3rem;
}

.loading {
  height: 50vh;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 2rem;
  font-weight: bold;
}

</style>