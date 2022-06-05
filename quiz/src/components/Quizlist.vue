<template> 
    <div>
        <quiz  v-if="viewState === 'quizzes'" v-for="quiz in quizzes" :key="quiz.id" v-bind:quiz="quiz" v-on:view-quiz="viewQuiz"></quiz>

        <div class="ui cards" v-if="viewState === 'cards'">
            <flash-card v-for="card in this.selectedQuiz.cards" :key="card.id" v-bind:card="card"></flash-card>
        </div>

        


    </div>     
</template>








<script>

import Quiz from './Quiz.vue';
import FlashCard from './FlashCard.vue';

export default {
    props: ['quizzes'],
    components: {
        Quiz,
        FlashCard,
    },
    data() {
        return {
            selectedQuiz: {cards:[]},
            viewState: 'quizzes',
        }
    }, 
    methods: {
        viewQuiz(quiz) {
            this.selectedQuiz = quiz;
            this.viewState = 'cards';
        }
    }
}

</script>









<style>


</style>