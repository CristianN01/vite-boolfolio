<script>
import axios from 'axios';
import SingleProject from './SingleProject.vue';

export default {
    components: {
        SingleProject
    },
    data() {
        return {
            projects: [],
        }
    },
    methods:{
        getProjects(){
            axios.get('http://127.0.0.1:8000/api/project', {
                params: {
                
                }
            })
            .then((response) => {
                console.log(response.data.results.data);
                this.projects = response.data.results.data;
            })
            .catch(function (error) {
                console.log(error);
            }) 
        }
    },
    created(){
        this.getProjects();
    }
}
</script>

<template>
    
        <SingleProject v-for="project in projects" :author="project.author" :content="project.content" :title="project.title" :projectImage="project.image"/>
    
</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;

</style>