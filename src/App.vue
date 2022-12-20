<template>
  <div class="app">
    
    <!-- <p> {{ state.name }} - {{ state.age }} ({{ gender }})</p>

    <button @click="changeName('Luis')">Change Name</button>
    <button @click="changeAge('40')">Change Name</button> --> 
    <header>
    <div class="title">
    <img src="@/assets/heart.svg" alt="heart">
        <h1>Hyrule Jobs</h1>
    </div>
      <div class="order">
        <button @click="handleClick('title')">Order by title</button>
        <button @click="handleClick('salary')">Order by salary</button>
        <button @click="handleClick('location')">Order by location</button>
      </div>
    </header>
  
    <JobList :jobs="jobs" :order="order"/>



  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import Job from '@/types/Job'
import JobList from '@/components/JobsList.vue'
import OrderTerm from '@/types/OrderTerm';


const jobs = ref<Job[]>([
    { title: 'Farm worker', location: 'Lon lon ranch', salary: 30000, id: '1' },
    { title: 'Quarryman', location: 'Death mountain', salary: 40000, id: '2' },
    { title: 'Flute player', location: 'The lost woods', salary: 35000, id: '3' },
    { title: 'Fisherman', location: 'Lake hylia', salary: 21000, id: '4' },
    { title: 'Prison guard', location: 'Gerudo valley', salary: 32000, id: '5' }
])

const order = ref<OrderTerm>('title')

const handleClick = (term: OrderTerm) => {
    order.value = term    
}


// const state = reactive({
//     name: 'Link' as string,
//     age: 31 as string | number
// })

// const state = ref({
//     name: "Link" as string,
//     age: 31 as string | number
// })

// const gender = ref<string>('Male')


// // console.log(state);

// const changeName = (name: string) => { 
//     state.value.name = name
//     return state.value.name
// }

// const changeAge = (age: number | string) => {
//     state.value.age = age
//     return state.value.age
// }


</script>

<style>
  header {
    text-align: center;
  }
  header .order {
    margin-top: 20px;
  }
  button {
    margin: 0 10px;
    color: #1195c9;
    border: 3px solid #1195c9;
    background: #d5f0ff;
    padding: 8px 16px;
    border-radius: 4px;
    cursor: pointer;
    font-weight: bold;
  }
  header .title{
    display: flex;
    justify-content: center;
  }
  header img {
    width: 60px;
    margin-right: 20px;
  }
  header h1 {
    font-size: 3em;
  }
</style>
