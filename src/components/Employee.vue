<template>
  <div class="employee">
    <h2 class="employee__name">{{employee.name}}</h2>
    <p class="employee__job">{{employee.job_title}}</p>
    <p class="employee__department">in {{employee.department}} department</p>
    <p class="employee__company">@ {{employee.company_name}}</p>
  </div>
</template>

<script>
export default {
  name: "Employee",
  props: {
    employee: {
      type: Object
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

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