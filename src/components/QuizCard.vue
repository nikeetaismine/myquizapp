<script setup lang="ts">
import { ref } from "vue";

const questions = ref ([
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
]);


</script>

<template>
    <div class="wrapper">

        <form action="">

            <div>
                <input type="">
                <label for=""></label>
            </div>
        </form>
    </div>

</template>

<style scoped>

.wrapper {
    height: 300px;
    width: 400px;
    background-color: #fff;
    border-radius: 10px;
}
</style>
