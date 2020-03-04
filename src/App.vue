<template>
    <cvContainer v-bind:cvData="cvData"/>
</template>

<script>
import cvContainer from './components/cvContainer.vue';
import cvData from './cvdata.js';

export default {
    title: 'Sazib CV Online',
    name: 'App',
    components: {
        cvContainer,
    },
    data () {
        return {
            cvData: cvData,
            default: ()=>{}
        };
    },
};
</script>

<style>
body{
    margin: 0;
    padding: 0;
    font-size: 1rem;
    font-family: 'Montserrat', sans-serif;
}
</style>
