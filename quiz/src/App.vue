<template>

  <div id="app">
    <quizlist v-bind:quizzes="quizzes"></quizlist>
  </div>

</template>





<script>
import Quizlist from './components/Quizlist';

export default {
  name: 'App',
  components: {
    Quizlist
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
      },{
        title: 'Chapter 3',
        description: 'Sample description three',
        cards: [
          {
            term: "Some word",
            definition: "Some definition",
          }
        ]
      },{
        title: 'Chapter 4',
        description: 'Sample description four',
        cards: [
          {
            term: "Some word",
            definition: "Some definition",
          }
        ]
      },{
        title: 'Chapter 5',
        description: 'Sample description five',
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
  border-style:solid;
  border-width:.01px;
  border-color:black;
  box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.502);
}
.ui.centered.card:hover {
  background-color:rgba(0, 0, 0, 0.253);
  cursor:pointer;
}
.extra_content {
    color: rgb(0, 0, 0);
    margin-left:5px;
    margin-bottom:5px;
} 
</style>
