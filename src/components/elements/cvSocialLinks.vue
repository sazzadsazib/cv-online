<template>
    <div class="cv-socialLinks">
        <p class="title mb-3rem">Find Me In the Other Social Media</p>

        <div class="social-links">
            <img :src="medium" width="16px" />
            <a :href="socialLinksData.medium" target="_blank">{{ socialLinksData.medium }}</a>
        </div>
         <div class="social-links">
            <img :src="behance" width="16px" />
            <a :href="socialLinksData.behance" target="_blank">{{ socialLinksData.behance }}</a>
        </div>
         <div class="social-links">
            <img :src="ig" width="16px" />
            <a :href="socialLinksData.instagram" target="_blank">{{ socialLinksData.instagram }}</a>
        </div>
         <div class="social-links">
            <img :src="stackOverflow" width="16px" />
            <a :href="socialLinksData.stackoverlow" target="_blank">{{ socialLinksData.stackoverlow }}</a>
        </div>
         <div class="social-links">
            <img :src="defaultIcon" width="16px" />
            <a :href="socialLinksData.portfolio" target="_blank">{{ socialLinksData.portfolio }}</a>
        </div>
    </div>
</template>

<script>
import medium from './../../assets/images/social-icons/medium.svg';
import behance from './../../assets/images/social-icons/behance.svg';
import ig from './../../assets/images/social-icons/ig.svg';
import stackOverflow from './../../assets/images/social-icons/stackoverflow.svg';
import defaultIcon from './../../assets/images/social-icons/default.svg';

export default {
    props: ['socialLinksData'],
    data() {
        return {
            medium: medium,
            behance: behance,
            ig: ig,
            stackOverflow: stackOverflow,
            defaultIcon: defaultIcon,
        };
    },
};
</script>

<style scoped>
.cv-socialLinks {
    margin-top: 4rem;
}
.mb-3rem {
    margin-bottom: 3rem;
}
.social-links {
    margin: 2rem auto 1rem;
}
.social-links > img {
    margin-right: 20px;;
}
.social-links > a {
    font-weight: 500;
}
</style>
