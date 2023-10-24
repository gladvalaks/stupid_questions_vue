<script>
import QuestionAnswer from './QuestionAnswer.vue';

export default {
  components: {
    QuestionAnswer,
  },
  props: {
    questions: {
      type: Array,
      required: true
    }
  },
  emits:["add-answer"],
  
}
</script>

<template>
  <div>
    <div 
      v-for="question in questions"
      :key="question.id"       
      class="post"  
    >
      <div> {{ question.title }}</div>
      <div v-if="question.answer">
        {{ question.answer }}
      </div>
      <div v-else>
        <QuestionAnswer 
          :id="question.id" 
          @add-answer="(id, answerText) => $emit('add-answer', id, answerText)" 
        />
      </div>
    </div>
  </div>
</template>

<style>
.post {
  margin-top: 10px;
  border: 2px solid lightgreen;
  padding: 10px;
}

.question-form {
  display: flex;
  flex-direction: column;
}
</style>
