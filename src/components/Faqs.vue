<template>
    <div class="faqs">
        <div class="text_container">
            <div class="question_container" @click="toggleAnswer">
                <p :class="{ open_question: clicked }" class="question">{{ question }}</p>
                <img class="icon" :class="{ arrow: clicked }" src="../assets/images/icon-arrow-down.svg" />
            </div>
            <transition name="slide">
                <div v-if="clicked" class="answer">{{ answer }}</div>
            </transition>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';
const clicked = ref(false);
const props = defineProps({
    question: {
        type: String,
    },
    answer: {
        type: String,
    },
});
const toggleAnswer = () => {
    clicked.value = !clicked.value;
};
</script>

<style scoped>
.slide-enter-active,
.slide-leave-active {
    transition: all 0.6s ease-out;
}
.slide-enter-from {
    transform: translateY(-15px);
    opacity: 0;
}
.slide-leave-to {
    transform: translateY(-15px);
    opacity: 0;
}

.question_container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    cursor: pointer;
    min-width: 300px;
    margin-bottom: 1rem;
    border-bottom: 1px solid lightgray;
}
.question::selection,
.answer::selection {
    background: none;
}

.question {
    font-size: 1.3rem;
    font-weight: 500;
    color: rgb(87, 87, 103);
    margin-bottom: 0.7rem;
    transition: color 0.3s ease-in-out;
}
.question:hover {
    color: var(--Soft-red);
}
.answer {
    font-size: 1rem;
    font-weight: 400;
    color: rgb(78, 79, 88);
    margin-bottom: 0.7rem;
    line-height: 1.5;
    letter-spacing: 0.4px;
}
.open_question {
    color: var(--Soft-red);
}
.icon {
    transition: transform 0.3s ease-in-out;
    transform: translateY(-5px);
    transform-origin: top center;
}
.arrow {
    transform: rotate(180deg);
}
</style>
