<template>
  <div id="app">
    <quizlist v-bind:quizzes="quizzes"></quizlist>
    <createquiz v-on:createquiz="createQuiz"></createquiz>
  </div>
</template>





<script>

import Quizlist from './components/Quizlist';
import Createquiz from './components/Createquiz';


export default {
  name: 'App',
  components: {
    Quizlist,
    Createquiz
  },
  methods: {
    createQuiz(newQuiz) {
      this.quizzes.push({
        title: newQuiz.title,
        description: newQuiz.description,
        cards: [],
      });
    }
  },
  data() {
    return {
      quizzes: [{
        title: 'Chapter 1',
        description: 'Sample description',
        cards: [
          {
            term: "Some word",
            definition: "Some definition",
          },
          {
            term: "Another word",
            definition: "Another definition",
          },
        ]
      },{
        title: 'Chapter 2',
        description: 'Sample description two',
        cards: [
          {
            term: "Some word",
            definition: "Some definition",
          }
        ]
      
      
      }]
      
    }
  }
}
</script>




<style>
#app {
  margin-top: 60px;
}
.ui.centered.card {
  border-style: solid;
  border-width: 0.01px;
  border-color: rgba(0, 0, 0, 0.185);
  box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.502);
}
.ui.centered.card:hover {
  /* background-color: rgba(0, 0, 0, 0.131); */
  border-width:.2px;
  border-color:black;
  cursor: pointer;
}
.extra_content {
  color: rgb(0, 0, 0);
  margin-left: 5px;
  margin-bottom: 5px;
}

</style>
