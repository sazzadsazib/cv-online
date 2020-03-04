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
        </div>
    </div>
</template>

<script>
import cvHeader from './elements/cvHeader';

export default {
    name: 'cvContainer',
    props: ['cvData'],
    components: { cvHeader },
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
</style>
