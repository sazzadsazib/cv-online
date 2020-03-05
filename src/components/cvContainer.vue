<template>
    <div class="cv-container">
        <div class="cv-content">
            <cvHeader
                v-bind:headerData="{
                    avatar: cvData.avatar,
                    name: cvData.name,
                    designation: cvData.designation,
                    githubLink: cvData.githubLink,
                    linkedIn: cvData.linkedIn,
                    dribbble: cvData.dribbble,
                }"
            />
            <cvFieldOfWork v-bind:fieldOfWorkData="cvData.fieldOfWork" />

            <div class="cv-section-divide__container">
                <div class="first-section">
                    Education
                </div>
                <div class="second-section">
                    Experiance
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import cvHeader from './elements/cvHeader';
import cvFieldOfWork from './elements/cvFieldOfWork';

export default {
    name: 'cvContainer',
    props: ['cvData'],
    components: { cvHeader, cvFieldOfWork },
};
</script>

<style scoped>
.cv-container {
    width: 100%;
    min-height: 100vh;
    overflow-x: hidden;
    background: url('./../assets/images/background.svg') no-repeat;
    background-size: cover;
    background-attachment: fixed;
}
.cv-content {
    padding: 4rem 8rem;
}
.cv-content__bg {
    width: 80%;
    position: absolute;
    top: 10rem;
    right: 0rem;
}

.cv-section-divide__container {
    display: flex;
}
.cv-section-divide__container > .first-section {
    flex: 0.9;
}
.cv-section-divide__container > .second-section {
    flex: 1.1;
}

/* just mobile */
@media only screen and (max-width: 700px) {
    .cv-content {
        padding: 2rem;
    }
    .cv-section-divide__container {
        flex-direction: column-reverse;
    }
}
</style>
