<script>
export default {
    data(){
        return{
            title: ""
        }
    },
    methods: {
        newQuestion() {
            const question = {
                id: Date.now(),
                title: this.title
            };
            this.$emit('addQuestion',question);
            console.log(1);
        },
        clearInputs() {
            this.title = "";
        }
    }
}
</script>

<template>
  <div>
    <form class = "question-form" @submit.prevent>
      <h4> Задайте свой глупый вопрос</h4>
      <input type="text" v-model="title" placeholder="Введите название вашего вопроса" class="input-question">
      <button @click="newQuestion" class = "button-question">Задать вопрос</button>
    </form>
  </div>
</template>

<style>

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
