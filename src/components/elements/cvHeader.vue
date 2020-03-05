<template>
    <div class="cv-container__header">
        <img :src="headerData.avatar" class="cv-container__header__avatar" />
        <div class="header-body">
            <P class="title">{{ headerData.name }}</P>
            <P class="subtitle">{{ headerData.designation }}</P>
            <div class="header-body__social">
                <div class="header-body__social__elements">
                    <a :href="headerData.githubLink.link" target="_blank"
                        ><img :src="githubIcon" />
                        {{ headerData.githubLink.title }}</a
                    >
                </div>
                <div class="header-body__social__elements">
                    <a :href="headerData.githubLink.link" target="_blank"
                        ><img :src="linkedInIcon" />
                        {{ headerData.githubLink.title }}</a
                    >
                </div>
                <div class="header-body__social__elements">
                    <a :href="headerData.dribbble.link" target="_blank"
                        ><img :src="dribbbleIcon" />
                        {{ headerData.dribbble.title }}</a
                    >
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import githubIcon from '../../assets/images/github.svg';
import linkedInIcon from '../../assets/images/linkedin.svg';
import dribbbleIcon from '../../assets/images/dribbble.svg';

export default {
    name: 'cvHeader',
    props: ['headerData'],
    data() {
        return {
            githubIcon: githubIcon,
            linkedInIcon: linkedInIcon,
            dribbbleIcon: dribbbleIcon,
        };
    },
};
</script>

<style scoped>
.cv-container__header {
    display: flex;
    z-index: 2;
}
.cv-container__header__avatar {
    width: 250px;
    border-radius: 10px;
    box-shadow: 5px 15px 10px -8px #8e77519e;
}
.header-body {
    width: 100%;
}
.header-body > .title {
    font-size: 4rem;
    font-weight: 600;
    margin: 1rem 0 0 2rem;
}
.header-body > .subtitle {
    font-size: 1.5rem;
    letter-spacing: 0.5rem;
    font-weight: 500;
    color: #a5a7aa;
    margin: 0.5rem 0 0 2rem;
}
.header-body__social {
    margin-top: 3rem;
    display: flex;
    width: 100%;
}
.header-body__social__elements {
    flex: 1;
    margin-left: 2rem;
    width: 100%;
}
.header-body__social__elements > a {
    text-decoration: none;
    display: flex;
    align-items: center;
    font-size: 1.5rem;
    font-weight: 600;
    color: #333;
}

.header-body__social__elements > a > img {
    width: 40px;
    margin-right: 10px;
}

/* just mobile */
@media only screen and (max-width: 700px) {
    .cv-container__header {
        display: block;
    }
    .cv-container__header__avatar {
        width: 60%;
        margin: 0 auto;
        text-align: center;
        display: block;
    }
    .header-body > .title {
        font-size: 1.8rem;
        text-align: center;
        margin: 2rem 0 0;
    }
    .header-body > .subtitle {
        font-size: 1rem;
        margin: 1rem 0 0;
        text-align: center;
    }
    .header-body__social {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
    }

    .header-body__social__elements > a {
        text-decoration: none;
        display: flex;
        align-items: center;
        font-size: 3vmin;
        font-weight: 600;
        color: #333;
    }
    .header-body__social__elements {
        flex: auto;
        width: auto;
        margin-left: 0;
    }
    .header-body__social__elements > a > img {
        width: 20px;
        margin-right: 5px;
    }
    @media only screen and (max-width: 400px) {
        .header-body__social__elements {
            display: none;
        }
    }
}
</style>
