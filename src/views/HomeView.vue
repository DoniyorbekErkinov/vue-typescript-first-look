<template>
  <div class="home">
    <div class="buttons">
      <button :class="order == 'title' ? 'active' : ''" @click="handleCLick('title')">Order by Title</button>
      <button :class="order == 'salary' ? 'active' : ''" @click="handleCLick('salary')">Order by Salary</button>
      <button :class="order == 'location' ? 'active' : ''" @click="handleCLick('location')">Order by Location</button>
    </div>
    <JobListComponentVue :jobs="jobs" :order="order"/>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref} from 'vue';
import Job from '../types/Job'
import OrderTerm from '../types/OrderTerm'
import JobListComponentVue from '@/components/JobList.component.vue';
export default defineComponent({
  name: 'HomeView',
  components: {
    JobListComponentVue
  },
  setup() {
    const jobs = ref<Job[]>([
      {title: 'Frontend', location: 'Namangan', salary: 300, id: '1'},
      {title: 'Logistics manager', location: 'Namangan', salary: 2000, id: '2'},
      {title: 'Backend', location: 'Namangan', salary: 5000, id: '3'},
      {title: 'Bank manager', location: 'Namangan', salary: 4000, id: '4'}
    ])
    const order = ref<OrderTerm>('title')
    const handleCLick = (term: OrderTerm) => {
      order.value = term
    }
    return {
      jobs,
      order  ,          
      handleCLick
    } 
  }
});
</script>
<style scoped>
.buttons {
width: 70%;
margin:  0 auto;
}
.buttons button {
  width: 200px;
  height: 45px;
  font-size: 20px;
  background: transparent;
  margin: 0 10px;
  border: 1px solid #ade3eb;
  cursor: pointer;
  color: #0b7686;
}
.active {
  background: #f6f6f6 !important;
  border: none !important;
}
</style>
