<template>
  <div class="app w-full h-full text-center mt-14">
    Hello typescript

    <p>Hello {{name}} ({{age}})</p>

    <button @click="changeName('Nanvani')" class="border border-red-400 p-3"> Change Name </button>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from 'vue';
import Job from "./types/Job";

export default defineComponent({
  name: 'App',

  setup() {
    const state = reactive({
      name: "Neeraj",
      age: 21 as string | number
    })

    const jobs = ref<Job[]>([
      { title: 'developer', location: 'delhi', salary: 500000, id: 1 },
      { title: 'senior developer', location: 'noida', salary: 3000000, id: 2 },
      { title: 'junior developer', location: 'delhi', salary: 50000, id: 3 },
      { title: 'ui developer', location: 'up', salary: 100000, id: 4 },
      { title: 'content writer', location: 'gujrat', salary: 300000, id: 5 },
    ])

    return { ...toRefs(state) };
  },
  methods: {

    changeName(name: string) {
      this.name = name;
    }
  }
});
</script>

<style>
</style>
