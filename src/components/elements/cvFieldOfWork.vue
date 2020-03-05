<template>
    <div class="cv-fieldOfWork">
        <p class="title">Field Of Work</p>
        <div class="fieldOfWork-container">
            <div
                class="fieldOfWork-container__item"
                v-for="(image, index) in imageData"
                v-bind:key="image"
            >
                <img :src="image" />
                <p class="info">
                    {{ fieldOfWorkData[index] || index + ' Info' }}
                </p>
            </div>
        </div>
    </div>
</template>

<script>
import first from './../../assets/images/01.svg';
import second from './../../assets/images/02.svg';
import third from './../../assets/images/03.svg';
import fourth from './../../assets/images/04.svg';

export default {
    props: ['fieldOfWorkData'],
    data() {
        return {
            imageData: [first, second, third, fourth],
        };
    },
};
</script>

<style scoped>
.cv-fieldOfWork {
    margin-top: 4rem;
}
.cv-fieldOfWork > .title {
    font-size: 2rem;
    font-weight: 700;
    text-transform: uppercase;
}
.fieldOfWork-container {
    display: flex;
    justify-content: space-around;
    align-items: baseline;
}
.fieldOfWork-container__item {
    display: flex;
    flex-direction: column;
    align-items: center;
}
.fieldOfWork-container__item > img {
    width: 60px;
}
.fieldOfWork-container__item > p {
    margin-top: 2rem;
}

/* just mobile */
@media only screen and (max-width: 700px) {
    .cv-fieldOfWork > .title {
        font-size: 1.5rem;
        font-weight: 700;
        text-transform: uppercase;
    }
    .fieldOfWork-container {
        display: flex;
        justify-content: space-around;
        align-items: baseline;
        flex-wrap: wrap;
    }
    .fieldOfWork-container__item {
        margin: 1rem auto;
        min-width: 50%;
    }
    .fieldOfWork-container__item > img {
        width: 40px;
    }
    .fieldOfWork-container__item > p {
        margin-top: 1rem;
    }
}
</style>
