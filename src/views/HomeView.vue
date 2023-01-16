<template>
    <div class="home_view">
        <div class="content_box">
            <img class="woman_img" src="../assets/images/illustration-woman-online-mobile.svg" alt="woman" />
            <img class="box_img" src="../assets/images/illustration-box-desktop.svg" alt="box" />
            <h1>FAQ</h1>
            <Faqs
                v-for="(question, index) in questions"
                :key="index"
                :question="questions[index]"
                :answer="answers[index]"
            />
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
img {
    display: inline-block;
}
.woman_img {
    width: 180px;
    height: 180px;
    position: absolute;
    top: -105px;
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
    transform: translateY(100px);
}
/* change display for bigger devices */
.box_img {
    display: none;
}
h1 {
    font-size: 2.5rem;
    font-weight: 700;
    color: var(--Very-dark-blue);
    margin-bottom: 2rem;
}
</style>
