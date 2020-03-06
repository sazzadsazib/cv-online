<template>
    <div class="cv-project">
        <p class="title">
            Projects
        </p>

        <div class="projects-container">
            <div
                class="project-card"
                v-for="project in projectsData"
                v-bind:key="project.id"
            >
                <img :src="project.projectlogo" class="project-card__logo" />
                <p class="project-card__timespan">{{ project.timespan }}</p>
                <div class="project-card__info">
                    <a
                        v-if="project.link"
                        :href="project.link"
                        rel="noreferrer noopener"
                        target="_blank"
                        ><i class="link-icon"></i
                    ></a>
                    <strong>{{ project.company }}</strong>
                    <span class="project-card__info-responsiblity"
                        >- {{ project.responsiblity }}</span
                    >
                </div>

                <p class="project-card__description">
                    {{ project.description }}
                </p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['projectsData'],
};
</script>

<style scoped>
.cv-project {
    margin-top: 4rem;
}
.projects-container {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    margin-top: 2rem;
}
.project-card {
    flex: 1;
    min-width: 46%;
    margin-right: 4%;
    margin-top: 1rem;
}
.project-card__timespan {
    text-transform: uppercase;
    font-size: 0.8rem;
    color: grey;
    margin-top: 1rem;
}
.project-card__logo {
    height: 2rem;
}
.project-card__info {
    display: flex;
    align-items: center;
}
.project-card__description {
    text-align: justify;
    font-size: 1rem;
    color: #4f535a;
    line-height: 1.7rem;
}
/* just mobile */
@media only screen and (max-width: 700px) {
    .project-card {
        min-width: 100%;
        margin-right: 0;
    }
    .project-card__info {
        flex-wrap: wrap;
    }
    .project-card__info-responsiblity {
        font-size: 0.8rem;
        color: grey;
        margin-top: 0.6rem;
        margin-bottom: 0.6rem;
    }
}
</style>
