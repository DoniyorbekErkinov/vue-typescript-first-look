<template>
  <div class="home">
    <JobListComponentVue :jobs="jobs"/>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref} from 'vue';
import Job from '../types/Job'
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
    return {
      jobs
    }
  }
});
</script>
<style>
</style>
