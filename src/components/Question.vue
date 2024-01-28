<script setup>
import { ref } from "vue";
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

