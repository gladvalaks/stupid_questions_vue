<script>
export default {
  props: {
    questions: {
        type: Array,
        required: true
    }
  }

  
}
</script>

<template>
  <div>
    <div class="post" v-for="question in questions">
      <div> {{ question.title }}</div>
      <div v-show="question.answer">{{ question.answer }}</div>
    </div>
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
.question-form{
  display: flex;
  flex-direction: column;
}
.input-question{
  margin-top: 10px;
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
}
.button-question{
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;

}
</style>
