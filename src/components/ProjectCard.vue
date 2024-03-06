<script>
export default {
    name: 'ProjectCard',
    props: {
        project: Object,
    }
}
</script>

<template>
    <div class="col-3">
        <router-link :to="{ name: 'project', params: { id: project.id } }">
        
            <div class="card my-2">
                <div class="card-title">
    
                    <h2 class="text-center">
                        {{ project['title'] }}
                    </h2>
                </div>
                <div class="card-body">
                   <p>{{ project['description'] }}</p>
                   <span>{{ project['end_date'] }}</span>
                </div>
            </div>
        </router-link>
        <div>
            {{ project.desc }}
        </div>
    </div>
</template>

<style lang="scss" scoped>
</style>
