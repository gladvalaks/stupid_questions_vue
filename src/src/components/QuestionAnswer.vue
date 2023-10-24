<script>
export default {
  props: {
    id: {
      type: Number,
      required: true
    }
  },
  emits:["add-answer"],
  data() {
    return {
      answerText: ""
    }
  },
  methods: {
    addAnswer() {
      if (this.answerText.length > 3) {
        this.$emit("add-answer", this.id, this.answerText);
        console.log(this.id);
      }
    }
  }
}
</script>
<template>
  <form 
    class="answer-form"
    @submit.prevent    
  >
    <input 
      v-model="answerText"
      type="text"       
      class="answer-question" 
      placeholder="Тут пока нет ответа, вы можете стать первым!"
    >

    <button 
      class="button-question"
      @click="addAnswer"      
    >
      Добавить новый вопрос
    </button>
  </form>
</template>
<style>
.answer-form{
  display: flex;
  flex-direction: column;
}
.answer-question {
  margin-top: 10px;
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

}
</style>