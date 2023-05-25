<template>
    <div>
        <h1>Jobs</h1>
        <div v-for="job in jobs" :key="job.id">
            <RouterLink :to="{name: 'job-details', params: {id: job.id}}">{{ job.title }}</RouterLink>
            <p>{{ job.details }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'JobsView',
    data() {
        return {
            jobs: [
                { title: 'Ninja', id: 1, details: 'You will be a ninja' },
                { title: 'Samurai', id: 2, details: 'You will be a samurai' },
                { title: 'Ronin', id: 3, details: 'You will be a ronin' }
            ]
        }
    }
}
</script>

<style>

</style>