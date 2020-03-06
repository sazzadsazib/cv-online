<template>
    <div class="cv-experiance">
        <p class="title">Work Experiance</p>
        <div
            class="experiance-container"
            v-for="experiance in experianceData"
            v-bind:key="experiance.id"
        >
            <p class="experiance-container__working-year">
                {{ experiance.year }}
            </p>
            <div>
                <p class="experiance-container__designation">
                    {{ experiance.designation }}
                </p>
                <p class="experiance-container__company-name">
                    {{ experiance.companyname }}
                </p>
                <p class="experiance-container__description">
                    {{ experiance.description }}
                </p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['experianceData'],
};
</script>

<style scoped>
.experiance-container {
    display: flex;
    justify-content: flex-start;
    margin-top: 2rem;
}

.experiance-container__working-year {
    margin-right: 2rem;
    min-width: 7rem;
}

.experiance-container__designation {
    font-weight: 500;
    font-size: 1.2rem;
    margin-top: 0.9rem;
    margin-bottom: 0px;
}
.experiance-container__company-name {
    font-weight: 400;
    font-size: 0.9rem;
    margin-top: 0.5rem;
    color: #4f535a;
}
.experiance-container__description {
    text-align: justify;
    font-size: 1rem;
    color: #4f535a;
    line-height: 1.7rem;
}

/* just mobile */
@media only screen and (max-width: 700px) {
    .experiance-container {
        display: block;
    }
    .experiance-container__working-year {
        margin-top: 2rem;
    }
    .experiance-container__description { 
        margin-top: 1.2rem;;
    }
}
</style>
