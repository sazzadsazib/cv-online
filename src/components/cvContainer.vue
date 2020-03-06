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
                    <cvEducation v-bind:educationData="cvData.education" />
                </div>
                <div class="second-section">
                    <cvExperiance v-bind:experianceData="cvData.experiance"/>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import cvHeader from './elements/cvHeader';
import cvFieldOfWork from './elements/cvFieldOfWork';
import cvEducation from './elements/cvEducation';
import cvExperiance from './elements/cvExperiance';

export default {
    name: 'cvContainer',
    props: ['cvData'],
    components: { cvHeader, cvFieldOfWork, cvEducation,cvExperiance },
};
</script>

<style>
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
    margin-top: 4rem;
}
.cv-section-divide__container > .first-section {
    flex: 0.9;
}
.cv-section-divide__container > .second-section {
    flex: 1.1;
}
.title {
    font-size: 2rem;
    font-weight: 700;
    text-transform: uppercase;
    margin: 0;
}

/* just mobile */
@media only screen and (max-width: 700px) {
    .cv-content {
        padding: 2rem;
    }
    .cv-section-divide__container {
        flex-direction: column-reverse;
    }
    .title {
        font-size: 1.5rem;
        font-weight: 700;
        text-transform: uppercase;
    }
}
</style>
