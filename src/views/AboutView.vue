<template>
  <div class="about">
     <p>{{name}} | {{age}}</p>
    <button @click="changeName('Doniyor')">Change Name</button>
    <button @click="changeAge(23)">Change Age</button>
  </div>
</template>
<script lang="ts">
import { defineComponent, reactive, toRefs } from 'vue';
export default defineComponent({
  name: 'HomeView',
  setup() {
    const state = reactive({
      name: 'Link',
      age: 22 as string | number
    })
    return {
      ...toRefs(state)
    }
    
  },
  methods: {
     changeName(name: string) {
      this.name = name
    },
    changeAge(age: number | string) {
      this.age = age
    } 
  }
});
</script>
