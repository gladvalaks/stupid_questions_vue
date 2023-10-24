<script>
export default {
  emits: ['add-question'],

  data() {
    return {
      title: ""
    }
  },

  methods: {
    newQuestion() {
      if (this.title.length<4){
        return
      }
      const question = {
        id: Date.now(),
        title: this.title,
        answer: ""
      };
      this.title = "";
      this.$emit('add-question', question);
      console.log("New Question");
    },

  }
}
</script>

<template>
  <div>
    <form 
      class="question-form" 
      @submit.prevent
    >
      <h4> Задайте свой глупый вопрос</h4>
      <input 
        v-model="title" 
        type="text"  
        placeholder="Введите название вашего вопроса" 
        class="input-question"
      >
      <button 
        class="button-question" 
        @click="newQuestion"
      > 
        Задать вопрос 
      </button>
    </form>
  </div>
</template>

<style>
.question-form {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.input-question {
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
