<script>
import QuestionForm from './QuestionForm.vue';
import QuestionsList from './QuestionsList.vue';

export default {
  components: { QuestionForm, QuestionsList },

  data() {
    return {
      questions: [
        { id: 1, title: "Как не биться головой о стену", answer: "Убиться до стены" },
      ],
    };
  },

  methods: {
    addQuestion(question) {
      this.questions.push(question);
    },

    addAnswer(id, answer) {
      console.log("newAnswer");
      this.questions.find(element => element.id == id)["answer"] = answer;
    }
  },
}
</script>

<template>
  <div class="content">
    <QuestionForm @add-question="addQuestion" />
    <QuestionsList 
      :questions="questions" 
      @add-answer="addAnswer"
    />
  </div>
</template>

<style>
* {
  padding: 0px;
  margin: 0px;
}

body {
  padding: 25px;
}
.content{
  width: 100%;
}
</style>
