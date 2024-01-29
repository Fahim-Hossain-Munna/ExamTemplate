<script setup>
import { ref } from "vue";

let ans = ref(0)

const questions = [
    {
        id:1,
        question: "What is the capital of France?",
        options: [
            { label: "Option A", value: "Paris" },
            { label: "Option B", value: "Berlin" },
            { label: "Option C", value: "Madrid" },
            { label: "Option D", value: "Rome" }
        ],
        correctAnswer: "Paris"
    },
    {
        id:2,
        question: "Which planet is known as the Red Planet?",
        options: [
            { label: "Option A", value: "Earth" },
            { label: "Option B", value: "Mars" },
            { label: "Option C", value: "Jupiter" },
            { label: "Option D", value: "Venus" }
        ],
        correctAnswer: "Mars"
    },
    {
        id:3,
        question: "In which year did World War II end?",
        options: [
            { label: "Option A", value: "1943" },
            { label: "Option B", value: "1945" },
            { label: "Option C", value: "1950" },
            { label: "Option D", value: "1939" }
        ],
        correctAnswer: "1945"
    },
    {
        id:4,
        question: "What is the largest mammal in the world?",
        options: [
            { label: "Option A", value: "Elephant" },
            { label: "Option B", value: "Blue Whale" },
            { label: "Option C", value: "Giraffe" },
            { label: "Option D", value: "Hippopotamus" }
        ],
        correctAnswer: "Blue Whale"
    },
    {
        id:5,
        question: "Who wrote 'Romeo and Juliet'?",
        options: [
            { label: "Option A", value: "William Shakespeare" },
            { label: "Option B", value: "Jane Austen" },
            { label: "Option C", value: "Charles Dickens" },
            { label: "Option D", value: "Leo Tolstoy" }
        ],
        correctAnswer: "William Shakespeare"
    },
    {
        id:6,
        question: "What is the capital of Japan?",
        options: [
            { label: "Option A", value: "Beijing" },
            { label: "Option B", value: "Seoul" },
            { label: "Option C", value: "Tokyo" },
            { label: "Option D", value: "Bangkok" }
        ],
        correctAnswer: "Tokyo"
    },
    {
        id:7,
        question: "Which element has the chemical symbol 'H'?",
        options: [
            { label: "Option A", value: "Helium" },
            { label: "Option B", value: "Hydrogen" },
            { label: "Option C", value: "Hassium" },
            { label: "Option D", value: "Hafnium" }
        ],
        correctAnswer: "Hydrogen"
    },
    {
        id:8,
        question: "Who painted the Mona Lisa?",
        options: [
            { label: "Option A", value: "Vincent van Gogh" },
            { label: "Option B", value: "Pablo Picasso" },
            { label: "Option C", value: "Leonardo da Vinci" },
            { label: "Option D", value: "Michelangelo" }
        ],
        correctAnswer: "Leonardo da Vinci"
    },
    {
        id:9,
        question: "What is the currency of Brazil?",
        options: [
            { label: "Option A", value: "Euro" },
            { label: "Option B", value: "Dollar" },
            { label: "Option C", value: "Yen" },
            { label: "Option D", value: "Real" }
        ],
        correctAnswer: "Real"
    },
    {
        id:10,
        question: "What is the largest ocean on Earth?",
        options: [
            { label: "Option A", value: "Atlantic Ocean" },
            { label: "Option B", value: "Indian Ocean" },
            { label: "Option C", value: "Southern Ocean" },
            { label: "Option D", value: "Pacific Ocean" }
        ],
        correctAnswer: "Pacific Ocean"
    }
];

let valueOfInput = ref([])

const submitAns = ()=>{
    ans.value = 0
   valueOfInput.value.forEach((res)=>{
        questions.forEach((q)=>{
            if(q.correctAnswer == res){
                ans.value = ans.value + 5 
            }
        })
   });

}



</script>


<template>
        <div class="max-w-md mx-auto py-8">
            <div class="flex justify-between items-center">
                <h1 class="text-2xl font-bold mb-4">Online Exam</h1>
                <p class="text-xl font-base mb-4">Total Mark :<span class="mb-4 text-[#D24545]">50</span></p>
            </div>
            <h2 class="text-2xl font-bold mb-4">Date : <span class="text-2xl font-semibold mb-4">{{ new Date() }}</span> </h2>
            
        </div>

        <div class="max-w-md mx-auto bg-white rounded px-8 py-3 shadow-md" v-for="(text,index) in questions" :key="text.id">
        <!-- Question Section -->
        <div class="mb-4">
            <h2 class="text-lg font-semibold mb-2">Question {{ ++index }}:</h2>
            <p class="text-gray-700">{{ text.question }}?</p>
        </div>

        <!-- Options Section -->
        <div class="mb-2">
            <label class="block text-sm font-medium text-gray-700">Options:</label>
            <div class="mt-2 flex flex-col">
                <label class="">
                    <input type="checkbox" class="form-radio text-indigo-600"  :value=text.options[0].value v-model="valueOfInput">
                    <span class="ml-2">{{ text.options[0].value }}</span>
                </label>
                <label class="">
                    <input type="checkbox" class="form-radio text-indigo-600"  :value=text.options[1].value v-model="valueOfInput">
                    <span class="ml-2">{{ text.options[1].value }}</span>
                </label>
                <label class="">
                    <input type="checkbox" class="form-radio text-indigo-600"  :value=text.options[2].value v-model="valueOfInput">
                    <span class="ml-2">{{ text.options[2].value }}</span>
                </label>
                <label class="">
                    <input type="checkbox" class="form-radio text-indigo-600"  :value=text.options[3].value v-model="valueOfInput">
                    <span class="ml-2">{{ text.options[3].value }}</span>
                </label>
            </div>
        </div>

    </div>
        <div class="max-w-md mx-auto bg-white rounded p-8 shadow-md">
            <!-- Submit Button -->
        <button class="bg-indigo-500 text-white px-4 py-2 rounded hover:bg-indigo-600" @click="submitAns">Submit Answer</button>
        </div>
</template>

