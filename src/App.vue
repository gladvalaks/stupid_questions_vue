<script>
import QuestionForm from './components/QuestionForm.vue';
import Question from './components/Question.vue';

export default {
  data() {
    return {
      questions: [
        { id: 1, title: "Как не биться головой о стену", answer: "Убиться до стены" },
        { id: 2, title: "Как не биться головой о стену", answer: "Убиться до стены" },
        { id: 3, title: "Как не биться головой о стену", answer: "Убиться до стены" },
        { id: 3, title: "Как не биться головой о стену" }
      ],

    };
  },
  methods: {
    addQuestion(question) {
            this.questions.push(question);
            this.clearInputs();
        },
  },
  components: { QuestionForm, Question }
}
</script>

<template>
  <div>
    <QuestionForm @addQuestion = "addQuestion" />
    <Question :questions="questions"></Question>
  </div>
</template>

<style>
* {
  padding: 0px;
  margin: 0px;
}

.post {
  margin-top: 10px;
  border: 2px solid lightgreen;
  padding-top: 5px;
}

body {
  padding: 25px;
}

.question-form {
  display: flex;
  flex-direction: column;
}

.input-question {
  margin-top: 10px;
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
}

.button-question {
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;

}</style>
