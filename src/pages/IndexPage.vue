<template>
  <q-page class="flex flex-center row">
    <div v-for="project in projects" :key="project.id" class="col-12 q-py-sm">
        <Singleproject :project=project />
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'
import axios from "axios"
import Singleproject from "../components/Singleproject.vue"

export default defineComponent({
    name: "IndexPage",
    data() {
        return {
            projects: [],
            uri: "http://localhost:3000/projects"
        };
    },
    mounted() {
        axios.get(this.uri)
            .then((response) => {
            this.projects = response.data;
        })
            .catch(err => console.log(err));
    },
    components: { Singleproject }
})
</script>

<style>
body {
  background-color: #F8F8F8;
}
</style>
