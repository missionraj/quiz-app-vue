<template>
    <form class="wrapper" @submit.prevent="submitAnswer">
        <div class="question">
            <h4> {{ selectedQuestion.question }} </h4>
            <div class="option" v-for="(item,index) in selectedQuestion.options" :key="index">
                <input type="radio" :id="`option${index}`" name="option" value="a" @change.prevent="selectOption(item)">
                <label :for="`option${index}`"> {{ item }} </label>
            </div>            
        </div>
        <button type="submit" class="btn" > submit </button>
    </form>
</template>

<script setup lang="ts">
import { ref } from "vue";

interface Question { 
    question:string;
    options:string[];
    correctAnswer:string;
}

const props =  defineProps<{ questions: Array<Question> }>()
const emit = defineEmits<{
  (e: 'selected', option:boolean ): void
}>()
const questionNo = ref(0);


const selectedQuestion = ref(props.questions[questionNo.value]);

const selctedOption = ref("");

const submitAnswer = () => {
    if(selctedOption.value == selectedQuestion.value.correctAnswer) { 
        emit("selected",true);
    } else { 
        emit("selected",false);
    }
    if (questionNo.value < props.questions.length) {
        questionNo.value++;
        selectedQuestion.value = props.questions[questionNo.value]   
    }
}

const selectOption = (option:string) => { 
    selctedOption.value = option;
    
} 
</script>

<style scoped>
.wrapper {
    height: 300px;
    width: 400px;
    background-color: #fff;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
}

.question { 
    flex: 1;
    padding: 10px;
}

.option {
    padding: 0.5rem 0.25rem;
}
.btn { 
    background-color: #4273F4;
    padding: 1rem 0.5rem;
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;
    text-align: center;
    color: #fff;
    cursor: pointer;
}

</style>