<template>
    <div class="cv-openSource">
        <p class="title">{{ openSourceData.title }}</p>
        <p class="p-text">{{ openSourceData.description }}</p>
        <p class="openSource__header">Contribution:</p>
        <div class="repo-container">
            <div
                class="repo-item"
                v-for="repo in openSourceData.contributedRepos"
                v-bind:key="repo.id"
            >
                <p class="repo-title">{{ repo.name }}</p>
                <a class="repo-link" :href="repo.link" target="_blank"
                    ><i class="link-icon" /> {{ repo.link }}</a
                >
            </div>
        </div>
        <p class="openSource__header">Packages:</p>
        <div class="repo-container">
            <div
                class="repo-item"
                v-for="repo in openSourceData.onenSourcedPackages"
                v-bind:key="repo.id"
            >
                <p class="repo-title">{{ repo.name }}</p>
                <a class="repo-link" :href="repo.link" target="_blank"
                    ><i class="link-icon" /> {{ repo.link }}</a
                >
            </div>
        </div>
    </div>
</template>

<script>

export default {
    props: ['openSourceData'],
};
</script>

<style scoped>
.cv-openSource {
    margin-top: 4rem;
}
.openSource__header {
    font-size: 1.2rem;
    font-weight: bold;
    margin-top: 2rem;
}
.repo-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    width: 60%;
}
.repo-title {
    font-weight: bold;
    font-size: 1rem;
}
.repo-title::before {
    content: '- ';
}
.repo-link {
    display: flex;
    align-items: center;
}
.repo-link > i {
    opacity: 0.5;
}
.repo-link:hover > i {
    opacity: 1;
}
</style>
