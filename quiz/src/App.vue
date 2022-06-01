<template>
  <div id="app">
    <div v-for="quiz in quizzes" class="ui centered card">
      <div class="content">
        <div class="header">
          {{ quiz.title }}
        </div>
        <div class="meta">
          {{ quiz.description }}
        </div>
      </div>
    </div>
  </div>
</template>





<script>

export default {
  name: 'App',
  components: {},
  data() {
    return {
      quizzes: [{title: 'Chapter 1',
      description: 'Sample description'
      },{title: 'Chapter 2',
      description: 'Sample description two'
      },{title: 'Chapter 3',
      description: 'Sample description three'
      },{title: 'Chapter 4',
      description: 'Sample description four'
      },{title: 'Chapter 5',
      description: 'Sample description five'
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
} 
</style>
