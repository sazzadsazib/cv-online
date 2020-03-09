<template>
    <div class="cv-journal">
        <p class="title">{{ journalData.linkTitle }}</p>
        <p class="journal_title"><q>{{ journalData.title }}</q></p>
        <p class="p-text">{{ journalData.description }}</p>
    </div>
</template>

<script>
export default {
    props: ['journalData'],
};
</script>

<style scoped>
.cv-journal {
    margin-top: 4rem;
}
q {
    quotes: '“' '”' '‘' '’';
}
q::before {
    content: open-quote;
}
q::after {
    content: close-quote;
}
.journal_title {
    margin-top: 2rem;
    font-weight: bold;
}
</style>
