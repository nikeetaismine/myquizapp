<script setup lang="ts">
import { ref } from "vue";

const questions = [
    {
        'question': "Which JavaScript data type can hold multiple values?",
        'answer': ["Array", "Number", "Object", "Boolean"],
        'correctAnswer': "Object"
    },
    {
        'question': "What will `typeof NaN` return?",
        'answer': ["'undefined'", "'number'", "'NaN'", "'object'"],
        'correctAnswer': "'number'"
    },
    {
        'question': "What is the output of `console.log([] + [])` in JavaScript?",
        'answer': ["[]", "'undefined'", "0", "'' (empty string)"],
        'correctAnswer': "'' (empty string)"
    },
    {
        'question': "Which of these is a valid way to declare a variable in JavaScript?",
        'answer': ["var", "let", "const", "All of the above"],
        'correctAnswer': "All of the above"
    },
    {
        'question': "What will `console.log(0.1 + 0.2 === 0.3)` output?",
        'answer': ["true", "false", "undefined", "NaN"],
        'correctAnswer': "false"
    },
    {
        'question': "What is the result of `typeof null` in JavaScript?",
        'answer': ["'object'", "'null'", "'undefined'", "'boolean'"],
        'correctAnswer': "'object'"
    },
    {
        'question': "What will `console.log([] == ![])` output?",
        'answer': ["true", "false", "undefined", "NaN"],
        'correctAnswer': "true"
    },
    {
        'question': "What does the following function return? `function f() {} return [typeof f];`",
        'answer': ["'function'", "'undefined'", "'null'", "'object'"],
        'correctAnswer': "'function'"
    },
    {
        'question': "Which statement will correctly catch an error in JavaScript?",
        'answer': ["catch(error)", "try {}", "try {} catch {}", "catch {} try {}"],
        'correctAnswer': "try {} catch {}"
    },
    {
        'question': "How many times does this loop run? `for (let i = 0; i < 5; i += 2) {}`",
        'answer': ["5 times", "3 times", "2 times", "Infinite times"],
        'correctAnswer': "3 times"
    }
];

const score = ref(0);
const questionCount = ref(1);
const selectedQuestion = ref(questions[0]);
const selectedOption = ref("");
const showForm = ref(true);

const submitAnswer = () => {
    console.log("sth submitted");

    if(selectedQuestion.value.correctAnswer == selectedOption.value) {
        score.value++;
        console.log("correct!")
    }

    if (questionCount.value < questions.length ) {
        selectedQuestion.value = questions[questionCount.value];
        questionCount.value++;
        selectedOption.value = "";
    } else {
        showForm.value = false;
    }
}

</script>

<template>
    <div class="wrapper">

        <form @submit.prevent="submitAnswer" v-if="showForm">
            <div class="question">
                <div class="q"> {{ questionCount }}) {{ selectedQuestion.question }} </div>
                <div class="option" v-for="(item, i) in selectedQuestion.answer">
                    <input type="radio" :id="`option${i}`" name="answer" :value="item" v-model="selectedOption">
                    <label class="custom-radio" :for="`option${i}`"></label>
                    <label class="optlabel" :for="`option${i}`">{{ item }}</label>
                </div>
                
            </div>
            
            <button type="submit">
                Submit
            </button>
        </form>
        <div class="score" v-if="!showForm">
            Your score is {{ score }} out of {{ questions.length }}
            <br>
            Refresh to start again...
        </div>
    </div>

</template>

<style scoped>

.wrapper {
    height: 400px;
    width: 400px;
    background-color: #fff;
    border-radius: 10px;
}

form {
    height: 100%;
    display: flex;
    flex-direction: column;
}

.question{
    flex: 1;
    padding: 1rem;
}

form > button {
    background-color:  rgb(231, 183, 198);
    border: none;
    padding: 1rem;
    color:  rgb(238, 62, 115);
    font-size: 20px;
    letter-spacing: 2px;
    cursor: pointer;
}

.q {
    color:  rgb(238, 62, 115);
    font-size: 20px;
    height: 90px;
}

.option {
    padding: 0.5em 0;
}

/* Hide the default radio button */
input[type="radio"] {
    display: none;
}

/* Custom radio button styling */
.custom-radio {
    cursor: pointer;
    padding: 0.5rem;
    position: relative;
    display: inline-block;
    border: 2px solid rgb(238, 62, 115);
    border-radius: 5px;
}

/* Style when the radio button is selected */
input[type="radio"]:checked + .custom-radio {
    background-color: rgb(238, 62, 115);
    color: #fff; /* Change label text color if needed */
}

input[type="radio"]:checked + .custom-radio:before {
    content: '';
    position: absolute;
    top: 50%;
    left: 3px;
    transform: translateY(-50%);
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background-color: white; /* Inner dot color */
}

.optlabel{
    color:  rgb(238, 62, 115);
    margin-left: 10px;
    font-size: 20px;
}

.score { 
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      color:  rgb(238, 62, 115);
      font-size: 30px;
  }

</style>
