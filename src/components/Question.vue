<script setup>
import { ref } from "vue";

const questions = [
    {
        id:1,
        question: "What is the capital of France?",
        options: ["Paris", "Berlin", "Madrid", "Rome"],
        correctAnswer: "Paris"
    },
    {
        id:2,
        question: "Which planet is known as the Red Planet?",
        options: ["Earth", "Mars", "Jupiter", "Venus"],
        correctAnswer: "Mars"
    },
    {
        id:3,
        question: "In which year did World War II end?",
        options: ["1943", "1945", "1950", "1939"],
        correctAnswer: "1945"
    },
    {
        id:4,
        question: "What is the largest mammal in the world?",
        options: ["Elephant", "Blue Whale", "Giraffe", "Hippopotamus"],
        correctAnswer: "Blue Whale"
    },
    {
        id:5,
        question: "Who wrote 'Romeo and Juliet'?",
        options: ["William Shakespeare", "Jane Austen", "Charles Dickens", "Leo Tolstoy"],
        correctAnswer: "William Shakespeare"
    },
    {
        id:6,
        question: "What is the capital of Japan?",
        options: ["Beijing", "Seoul", "Tokyo", "Bangkok"],
        correctAnswer: "Tokyo"
    },
    {
        id:7,
        question: "Which element has the chemical symbol 'H'?",
        options: ["Helium", "Hydrogen", "Hassium", "Hafnium"],
        correctAnswer: "Hydrogen"
    },
    {
        id:8,
        question: "Who painted the Mona Lisa?",
        options: ["Vincent van Gogh", "Pablo Picasso", "Leonardo da Vinci", "Michelangelo"],
        correctAnswer: "Leonardo da Vinci"
    },
    {
        id:9,
        question: "What is the currency of Brazil?",
        options: ["Euro", "Dollar", "Yen", "Real"],
        correctAnswer: "Real"
    },
    {
        id:10,
        question: "What is the largest ocean on Earth?",
        options: ["Atlantic Ocean", "Indian Ocean", "Southern Ocean", "Pacific Ocean"],
        correctAnswer: "Pacific Ocean"
    }
];
</script>


<template>

        <div class="max-w-md mx-auto py-8">
            <div class="flex justify-between items-center">
                <h1 class="text-2xl font-bold mb-4">Online Exam</h1>
                <p class="text-xl font-base mb-4">Total Mark : <span class="mb-4 text-[#D24545]">20</span></p>
            </div>
            <h2 class="text-2xl font-bold mb-4">Date : <span class="text-2xl font-semibold mb-4">{{ new Date() }}</span> </h2>
            
        </div>

        <div class="max-w-md mx-auto bg-white rounded p-8 shadow-md">
        <!-- Question Section -->
        <div class="mb-4">
            <h2 class="text-lg font-semibold mb-2">Question 1:</h2>
            <p class="text-gray-700">What is the capital of France?</p>
        </div>

        <!-- Options Section -->
        <div class="mb-6">
            <label class="block text-sm font-medium text-gray-700">Options:</label>
            <div class="mt-2 flex flex-col">
                <label class="">
                    <input type="radio" class="form-radio text-indigo-600" name="question1" value="option1" v-model="ans">
                    <span class="ml-2">Option A</span>
                </label>
                <label class="">
                    <input type="radio" class="form-radio text-indigo-600" name="question2" value="option2" v-model="ans">
                    <span class="ml-2">Option B</span>
                </label>
                <label class="">
                    <input type="radio" class="form-radio text-indigo-600" name="question3" value="option3" v-model="ans">
                    <span class="ml-2">Option C</span>
                </label>
                <label class="">
                    <input type="radio" class="form-radio text-indigo-600" name="question4" value="option4" v-model="ans">
                    <span class="ml-2">Option D</span>
                </label>
            </div>
        </div>

        <!-- Submit Button -->
        <button class="bg-indigo-500 text-white px-4 py-2 rounded hover:bg-indigo-600">Submit Answer</button>
    </div>
</template>

