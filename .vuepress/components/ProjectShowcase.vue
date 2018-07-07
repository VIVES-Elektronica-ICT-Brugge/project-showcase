<template>
    <section class="project-summary">
    <!-- <h2>Project Showcase</h2> -->
    <div class="project" v-for="page in projects()">
        <ProjectSummary :page="page"></ProjectSummary>
    </div>
    </section>
</template>

<script>
export default {
    methods: {
        projects() {
            return this.$site.pages
            .filter((page) => page.path.startsWith("/projects/"))
        }
    },
}
</script>

<style>
section.project-summary{
    display: grid;
    grid-template-columns:  auto auto;
    grid-gap: 20px;
}

section.project-summary .project{
    display: inline-grid;
}
</style>
