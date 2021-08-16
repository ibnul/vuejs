<template>
    <h1>Job Details </h1>
    <div v-if="job">
        <h2>{{ job.title }}</h2>
        <p>{{ job.details }}</p>
        <p>The Job id is {{ job.id }}</p>

    </div>
    <div v-else>
        <p>Loading job details ....</p>
    </div>
</template>

<script>
export default {
    props: ['id'],
    data(){
        return {
            job: null
        }
    },
    // data(){
    //     return{
    //         id: this.$route.params.id
    //     }
    // },
    mounted(){
        //console.log('http://localhost:3000/jobs/' + this.id);
        
        fetch('http://localhost:3000/jobs/' + this.id)
            .then( res => res.json())
            .then( data => this.job = data)
            .catch(err => console.log(err.message))
     
    }
}

</script>

<style>

</style>
