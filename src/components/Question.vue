<script setup>
import { ref } from "vue";
import { onMounted } from 'vue'
import { initFlowbite } from 'flowbite'

onMounted(() => {
    initFlowbite();
})

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
        <button data-modal-target="static-modal" data-modal-toggle="static-modal" class="bg-indigo-500 text-white px-4 py-2 rounded hover:bg-indigo-600" @click="submitAns">Submit Answer</button>
        </div>

        



<!-- Main modal -->
<div id="static-modal" data-modal-backdrop="static" tabindex="-1" aria-hidden="true" class="hidden overflow-y-auto overflow-x-hidden fixed top-0 right-0 left-0 z-50 justify-center items-center w-full md:inset-0 h-[calc(100%-1rem)] max-h-full">
    <div class="relative p-4 w-full max-w-2xl max-h-full">
        <!-- Modal content -->
        <div class="relative bg-white rounded-lg shadow dark:bg-gray-700">
            <!-- Modal header -->
            <div class="flex items-center justify-between p-4 md:p-5 border-b rounded-t dark:border-gray-600">
                <h3 class="text-xl font-semibold text-gray-900 dark:text-white">
                    Examination Overview
                </h3>
                <button type="button" class="text-gray-400 bg-transparent hover:bg-gray-200 hover:text-gray-900 rounded-lg text-sm w-8 h-8 ms-auto inline-flex justify-center items-center dark:hover:bg-gray-600 dark:hover:text-white" data-modal-hide="static-modal">
                    <svg class="w-3 h-3" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 14">
                        <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m1 1 6 6m0 0 6 6M7 7l6-6M7 7l-6 6"/>
                    </svg>
                    <span class="sr-only">Close modal</span>
                </button>
            </div>
            <!-- Modal body -->
            <div class="p-4 md:p-5 space-y-4">
                <p class="flex justify-center items-center text-2xl leading-relaxed text-gray-500 dark:text-gray-400 gap-2">
                    <span class="text-[#1B9C85] font-bold">Congretulations,</span><i class="fa-solid fa-graduation-cap  text-[#2D4356]"></i>
                </p>
                <div class="flex justify-center items-center">
                    <i class="fa-solid fa-star text-4xl text-[#F4D160]"></i>
                    <i class="fa-solid fa-star text-4xl text-[#F4D160]"></i>
                    <i class="fa-solid fa-star text-4xl text-[#F4D160]"></i>
                    <i class="fa-solid fa-star text-4xl text-[#F4D160]"></i>
                    <i class="fa-solid fa-star text-4xl text-[#F4D160]"></i>
                </div>
                <div class="flex justify-center items-center gap-4">
                    <img class="w-10 h-10 rounded-full" src="https://cdn.pixabay.com/photo/2015/10/05/22/37/blank-profile-picture-973460_1280.png" alt="">
                    <div class="font-medium dark:text-white">
                        <div>Mr. Guest</div>
                        <div class="text-sm text-gray-500 dark:text-gray-400">Your Result/Mark is : <span class="text-xl text-[#AF2655]">{{ ans }}</span> out of 50</div>
                    </div>
                </div>
            </div>
            <!-- Modal footer -->
            <div class="flex items-center p-4 md:p-5 border-t border-gray-200 rounded-b dark:border-gray-600">
                <button data-modal-hide="static-modal" type="button" class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">I accept</button>
                <button data-modal-hide="static-modal" type="button" class="ms-3 text-gray-500 bg-white hover:bg-gray-100 focus:ring-4 focus:outline-none focus:ring-blue-300 rounded-lg border border-gray-200 text-sm font-medium px-5 py-2.5 hover:text-gray-900 focus:z-10 dark:bg-gray-700 dark:text-gray-300 dark:border-gray-500 dark:hover:text-white dark:hover:bg-gray-600 dark:focus:ring-gray-600">Decline</button>
            </div>
        </div>
    </div>
</div>

</template>

