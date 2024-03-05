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
        <div>
            {{ project.desc }}
        </div>
    </div>
</template>

<style lang="scss" scoped>
</style>
