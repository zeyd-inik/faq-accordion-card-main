<template>
    <div class="home_view">
        <img class="box_img_desktop" src="../assets/images/illustration-box-desktop.svg" alt="box" />
        <div class="content_box">
            <img class="woman_img_mobile" src="../assets/images/illustration-woman-online-mobile.svg" alt="woman" />
            <div class="shadow"></div>
            <img class="woman_img_desktop" src="../assets/images/illustration-woman-online-desktop.svg" alt="woman" />
            <div class="text_container">
                <h1>FAQ</h1>
                <Faqs
                    v-for="(question, index) in questions"
                    :key="index"
                    :question="questions[index]"
                    :answer="answers[index]"
                />
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';
import Faqs from '../components/Faqs.vue';
const questions = ref([
    'How many team members can I invite?',
    'What is the maximum file upload size?',
    'How do I reset my password?',
    'Can I cancel my subscription?',
    'Do you provide additional support?',
]);
const answers = ref([
    'You can invite up to 2 additional users on the Free plan. There is no limit on team members for the Premium plan.',
    'No more than 2GB. All files in your account must fit your allotted storage space.',
    'Click “Forgot password” from the login page or “Change password” from your profile page. A reset link will be emailed to you.',
    'Yes! Send us a message and we’ll process your request no questions asked.',
    'Chat and email support is available 24/7. Phone lines are open during normal business hours.',
]);
</script>

<style scoped>
.home_view {
    padding-top: 9rem;
}
img {
    display: block;
}
.text_container {
    text-align: center;
}
.woman_img_mobile {
    width: 180px;
    height: 180px;
    position: absolute;
    top: -105px;
}
.shadow {
    width: 135px;
    height: 135px;
    background-color: rgb(58, 57, 125);
    border-radius: 5px;
    position: absolute;
    top: -55px;
    transform: rotate(45deg);
    transform-origin: center;
    opacity: 0.08;
    border-radius: 15px;
    rotate: x 53deg;
}
.content_box {
    width: 340px;
    background-color: var(--Light-grayish-blue);
    border-radius: 15px;
    padding: 5rem 2rem 2rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
    margin-top: auto;
    transition: all 1s ease-in-out;
}
/* mobile display none elements */
.box_img_desktop,
.woman_img_desktop {
    display: none;
}

h1 {
    font-size: 2.5rem;
    font-weight: 700;
    color: var(--Very-dark-blue);
    margin: 2rem;
}

/* media queries--------------------------------------------- */
@media (min-width: 768px) {
    /* bigger devices display none elements */
    .woman_img_mobile,
    .shadow {
        display: none;
    }

    .home_view {
        position: relative;
        padding-top: 0;
    }
    .content_box {
        width: 700px;
        flex-direction: row;
        padding: 2rem;
        overflow: hidden;
        position: static;
        transform: translateY(0);
    }
    .box_img_desktop {
        display: block;
        width: 100px;
        position: absolute;
        top: 170px;
        left: -55px;
        z-index: 99;
    }
    .woman_img_desktop {
        display: block;
        width: 250px;
        position: fixed;
        left: -40px;
        top: 97px;
    }

    .text_container {
        padding: 2rem;
        margin: -1rem 2rem 1rem auto;
        width: 400px;
    }
    h1 {
        text-align: left;
        margin-left: 0;
    }
}
</style>
