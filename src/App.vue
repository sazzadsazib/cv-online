<template>
    <div>
        <loader v-if="loading" />
        <cvContainer v-if="!loading" v-bind:cvData="cvData" />
    </div>
</template>

<script>
import cvContainer from './components/cvContainer.vue';
import cvData from './cvdata.js';
import loader from './components/elements/loader';

export default {
    title: 'Sazib CV Online',
    name: 'App',
    components: {
        cvContainer,
        loader,
    },
    data() {
        return {
            cvData: cvData,
            loading: true,
            default: () => {},
        };
    },
    mounted() {
        this.$nextTick(() => {
            setTimeout(()=>{
                this.loading = false;
            },1500)
        });
    },
};
</script>

<style>
body {
    margin: 0;
    padding: 0;
    font-size: 1rem;
    font-family: 'Montserrat', sans-serif;
    color: #232931;
}
</style>
