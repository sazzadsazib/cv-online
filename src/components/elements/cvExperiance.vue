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
                    <a
                        v-if="experiance.link"
                        :href="experiance.link"
                        rel="noreferrer noopener"
                        target="_blank"
                        ><i class="company-link"></i
                    ></a>
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
.cv-experiance {
    border-left: 1px solid lightgrey;
    padding-left: 40px;
}
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
    display: flex;
    align-items: center;
}
.experiance-container__company-name > a > i {
    margin-left: 15px;
    cursor: pointer;
    color: #4f535aae;
}
.experiance-container__description {
    text-align: justify;
    font-size: 1rem;
    color: #4f535a;
    line-height: 1.7rem;
}

/* icon */

.company-link {
    box-sizing: border-box;
    position: relative;
    display: block;
    transform: rotate(-45deg) scale(var(--ggs, 1));
    width: 8px;
    height: 2px;
    background: currentColor;
    border-radius: 4px;
}
.company-link::after,
.company-link::before {
    content: '';
    display: block;
    box-sizing: border-box;
    position: absolute;
    border-radius: 3px;
    width: 8px;
    height: 10px;
    border: 2px solid;
    top: -4px;
}
.company-link::before {
    border-right: 0;
    border-top-left-radius: 40px;
    border-bottom-left-radius: 40px;
    left: -6px;
}
.company-link::after {
    border-left: 0;
    border-top-right-radius: 40px;
    border-bottom-right-radius: 40px;
    right: -6px;
}

/* just mobile */
@media only screen and (max-width: 700px) {
    .cv-experiance {
        border: none;
        padding-left: 0;
    }
    .experiance-container {
        display: block;
    }
    .experiance-container__working-year {
        margin-top: 2rem;
    }
    .experiance-container__description {
        margin-top: 1.2rem;
    }
}
</style>
