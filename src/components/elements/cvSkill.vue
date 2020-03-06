<template>
    <div class="cv-skill">
        <p class="title">Skill</p>

        <div class="skill-list">
            <div
                class="skill-list-container"
                v-for="(skillTitle, i) in Object.keys(skillsData)"
                v-bind:key="i"
            >
                <!-- sounds wrong ^ -->
                <p class="skill-list__title">
                    {{ skillTitle }}
                </p>

                <div
                    class="skill-list__list"
                    v-for="(skill, index2) in skillsData[skillTitle]"
                    v-bind:key="index2"
                >
                    <i class="skill-highlighter"></i> {{ skill }}
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['skillsData'],
};
</script>

<style scoped>
.cv-skill {
    margin-top: 1rem;
}

.skill-list {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
}
.skill-list-container {
    flex: 1;
    min-width: 15rem;
}
.skill-list__title {
    text-transform: uppercase;
    font-weight: 600;
    color: #4f535a;
    font-size: 1rem;
    margin-bottom: 0.5rem;
    margin-top: 2rem;
    margin-bottom: 1rem;
}

.skill-list__list {
    display: flex;
    align-items: center;
    padding: 5px 0;
}

.skill-list__list > i {
    margin-right: 1rem;
}

/* icon */

.skill-highlighter {
    box-sizing: border-box;
    position: relative;
    display: block;
    transform: scale(var(--ggs, 1));
    width: 10px;
    height: 10px;
    border: 2px solid transparent;
    box-shadow: 0 0 0 2px;
    border-radius: 100px;
    overflow: hidden;
}
.skill-highlighter::before {
    content: '';
    display: block;
    box-sizing: border-box;
    position: absolute;
    width: 4px;
    height: 4px;
    border: 2px solid;
    border-radius: 3px;
    left: 1px;
    top: 1px;
}

/* just mobile */
@media only screen and (max-width: 700px) {
    .skill-list-container {
        min-width: 10rem;
    }
}
</style>
