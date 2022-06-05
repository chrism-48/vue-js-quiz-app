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
      const maxId = Math.max.apply(Math, this.quizzes.map(function(q) {return q.id}));
      const nextId = maxId + 1;
      this.quizzes.push({
        id: nextId,
        title: newQuiz.title,
        description: newQuiz.description,
        cards: [],
      });
    }
  },
  data() {
    return {
      quizzes: [{
        id: 1,
        title: 'Chapter 1',
        description: 'Sample description',
        cards: [
          {
            id: 1,
            term: "Some word",
            definition: "Some definition",
          },
          {
            id: 2,
            term: "Another word",
            definition: "Another definition",
          },
        ]
      },{
        id: 2,
        title: 'Chapter 2',
        description: 'Sample description two',
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
      
      
      }]
      
    }
  }
}
</script>




<style>
#app {
  margin-top: 20px;
}
body {
  background-position: center center;
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-image: url('./assets/luke-chesser-3rWagdKBF7U-unsplash.jpg');
}
.ui.centered.card {
  border-style: solid;
  border-color: rgba(0, 0, 0, 0.247);
  border-width: .01px; 
  box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.502);
}
.ui.centered.card:hover {
  border-width:1.2px;
  border-color:black;
  cursor: pointer;
  box-shadow:2px 2px 12px rgba(0, 0, 0, 0.658) !important;
  
}
.extra_content {
  color: rgb(0, 0, 0);
  margin-left: 5px;
  margin-bottom: 5px;
}

</style>
