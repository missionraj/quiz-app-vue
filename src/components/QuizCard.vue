<template>
    <div class="wrapper">
        <form @submit.prevent="submitAnswer" v-if="!showScore" >
            <div class="question">

            <div class="q"> {{ questionCount }}) {{ selctedQuestion.question }} </div>
            <div class="option" v-for="(item, i) in selctedQuestion.answers">
                <input type="radio" :id="`option${i}`" name="answers" v-model="selectedOption" :value="item">
                <label :for="`option${i}`" > {{ item }} </label>
            </div>
            </div>
            <button type="submit">
                submit
            </button>
        </form>
        <div class="score" v-else>
            score is {{ score }} out of {{ questions.length }}
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const questions = [
    {
        "question":"what is 1 + 1 ",
        "answers":["2","3","6","7"],
        "correctAnswer":"2"
    },
    {
        "question":"what is 2 * 2 ",
        "answers":["2","3","4","10"],
        "correctAnswer":"4"
    },
    {
        "question":"what is 10 / 5 ",
        "answers":["2","5","6","7"],
        "correctAnswer":"2"
    },
    {
        "question":"what is 3 + 2",
        "answers":["5","3","6","7"],
        "correctAnswer":"5"
    },
    {
        "question":"what is 7 - 6  ",
        "answers":["1","3","6","7"],
        "correctAnswer":"1"
    }
]

const score = ref(0);
const questionCount = ref(1);
const selectedOption = ref("");
const showScore = ref(false);

const selctedQuestion = ref(questions[0]);

const submitAnswer = () => { 
    if (selctedQuestion.value.correctAnswer == selectedOption.value) {
        score.value++;
    }
    if (questionCount.value < questions.length ) {
        selctedQuestion.value = questions[questionCount.value];
        questionCount.value++
        selectedOption.value = "";
    } else { 
        showScore.value = true;
    }
        
}

</script>

<style scoped>
  .wrapper { 
      height: 300px;
      width: 400px;
      background-color: #fff;
      border-radius: 10px;
  }

  form {
      height: 100%;
      display: flex;
      flex-direction: column;
  }

  .question {
      flex: 1;
      padding: 1rem;
  }

  form > button { 
      background-color: #4273F4;
      border:none;
      padding: 1rem;
      color: #fff;
      font-size: 16px;
      letter-spacing: 1px;
      cursor: pointer;
  }

  .q {
      height: 40px;
  }

  .option {
      padding: 0.5em 0;
  }
  .score { 
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
  }
</style>