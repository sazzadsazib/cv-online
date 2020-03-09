<template>
    <div class="cv-fieldInterested">
        <p class="title">Field Of Interest</p>
        <p class="p-text description">{{ fieldInterestedData }}</p>
    </div>
</template>

<script>
export default {
    props: ['fieldInterestedData'],
};
</script>

<style scoped>
.cv-fieldInterested {
    margin-top: 4rem;
}
.description {
    /* scoped so no need to think about overlap */
    margin-top: 1rem;
}
</style>
