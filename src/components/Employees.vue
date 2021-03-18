<template>
  <div>
    <div class="loading" v-if="loading">
      Loading
    </div>
    <div class="employees" v-else>
      <div class="employee"  v-for="employee in employees" :key="employee.id">
        <h2 class="employee__name">{{employee.name}}</h2>
        <p class="employee__job">{{employee.job_title}}</p>
        <p class="employee__department">in {{employee.department}} department</p>
        <p class="employee__company">@ {{employee.company_name}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Employees",
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

.employee {
  width: 40%;
  border-radius: 5px;
  margin: 1rem;
  padding: 1rem;
  background-color: #ecf0f1;
}

@media screen and (max-width: 450px) {
  .employee {
    width: 100%;
  }
}

.employee:hover {
  transform: scale(1.05);
  transition: .2s ease-in-out;
}

.employee__name {
  font-size: 1.5rem;
  font-weight: bold;
  margin-bottom: .5rem;
}

.employee__job {
  font-size: 1.2rem;
  font-style: italic;
  margin-bottom: .5rem;
}

.employee__department {
  margin-bottom: .5rem;
}

.employee__company {
  text-transform: uppercase;
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