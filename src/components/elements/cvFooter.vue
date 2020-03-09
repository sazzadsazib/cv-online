<template>
    <div>
        <div class="'sign">
            <img :src="sign" class="sign_element" />
        </div>
        <div class="cv-footer">
            <div class="footer-container">
                <div>
                    <p class="text-center footer-text">{{ info.phone }}</p>
                    <p class="text-center footer-detail">Phone</p>
                </div>
                <div>
                    <p class="text-center footer-text">{{ info.address }}</p>
                    <p class="text-center footer-detail">Address</p>
                </div>
                <div>
                    <p class="text-center footer-text">{{ info.email }}</p>
                    <p class="text-center footer-detail">Email</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import sazzad from './../../assets/images/sazzad.svg';
export default {
    props: ['info'],
    data() {
        return {
            sign: sazzad,
        };
    },
};
</script>

\
<style scoped>
.cv-footer {
    margin: 4rem auto 0rem;
    padding: 2rem;
    background: rgba(66, 66, 66, 0.356);
    display: block;
}
.footer-container {
    display: flex;
    justify-content: space-around;
    margin-top: -4.5rem;
}
.footer-detail {
    opacity: 0.3;
    color: white;
    font-weight: bold;
}
.sign {
    width: 100%;
}
.sign_element {
    width: 120px;
    display: flex;
    justify-content: center;
    margin: 0 auto;
}
.footer-text {
    font-size: 1rem;
}

/* just mobile */
@media only screen and (max-width: 700px) {
    .sign_element {
        width: 40%;
        display: flex;
        justify-content: center;
        margin: 0 auto;
    }
    .footer-text {
        font-size: 0.7rem;
    }
    .footer-detail {
        font-size: 0.8rem;
    }
    .footer-container {
        margin-top: -4rem;
    }
}
</style>
