<template>
    <div class="loader-container">
        <div>
            <i class="loader"></i>
        </div>
        <p class="loader__description">Loading Sazzad's CV</p>
    </div>
</template>
<script>
export default {
    name: 'Loader',
};
</script>

<style scoped>
.loader {
    transform: scale(var(--ggs, 1));
}
.loader,
.loader::after,
.loader::before {
    box-sizing: border-box;
    position: relative;
    display: block;
    width: 60px;
    height: 60px;
}
.loader::after,
.loader::before {
    content: '';
    position: absolute;
    border-radius: 100px;
}
.loader::before {
    animation: spinner 1s cubic-bezier(0.6, 0, 0.4, 1) infinite;
    border: 8px solid transparent;
    border-top-color: currentColor;
}
.loader::after {
    border: 9px solid;
    opacity: 0.2;
}
@keyframes spinner {
    0% {
        transform: rotate(0deg);
    }
    to {
        transform: rotate(359deg);
    }
}
.loader-container {
    display: flex;
    height: 100vh;
    width: 100%;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}
.loader__description {
    margin-top: 2rem;
    font-size: 0.8rem;
    font-weight: 400;
    letter-spacing: 0.2rem;
}
</style>
