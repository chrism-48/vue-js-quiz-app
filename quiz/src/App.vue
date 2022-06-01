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
      }]
      
      
    }
  }
}
</script>




<style>
#app {  
  margin-top: 60px;
}
</style>
