<template>
    <div>
        <h1>Jobs</h1>
        <div v-if="jobs.length">
            <div v-for="job in jobs" :key="job.id">
                <RouterLink :to="{name: 'job-details', params: {id: job.id}}">{{ job.title }}</RouterLink>
                <p>{{ job.details }}</p>
            </div>
        </div>
        <div v-else>
            <p>Loading...</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'JobsView',
    data() {
        return {
            // data hardcoded
            // jobs: [
            //     { title: 'Ninja', id: 1, details: 'You will be a ninja' },
            //     { title: 'Samurai', id: 2, details: 'You will be a samurai' },
            //     { title: 'Ronin', id: 3, details: 'You will be a ronin' }
            // ]
            // data fetched from API
            jobs: []
        }
    },
    mounted() {
        fetch('http://localhost:3000/jobs')
            .then(response => response.json())
            .then(data => {
                this.jobs = data
            })
            .catch(error => console.log(error.message))
    },
}
</script>

<style>

</style>