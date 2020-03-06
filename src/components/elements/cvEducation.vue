<template>
    <div class="cv-education">
        <p class="title">Education</p>
        <div
            class="education-container"
            v-for="education in educationData"
            v-bind:key="education.id"
        >
            <p class="education-container__year">
                {{ education.year }}
            </p>
            <div>
                <p class="education-container__grad-title">
                    {{ education.degree }}
                </p>
                <p class="education-container__grad-institute">
                    {{ education.institute }}
                    <strong v-if="education.result">{{
                        `(${education.result})`
                    }}</strong>
                </p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['educationData'],
};
</script>

<style scoped>
.education-container {
    display: flex;
    justify-content: flex-start;
    margin-top: 2rem;
}

.education-container__year {
    margin-right: 2rem;
    min-width: 6rem;
}
/* just mobile */
@media only screen and (max-width: 700px) {
    .cv-education {
        margin-top: 3rem;
    }
}
</style>
