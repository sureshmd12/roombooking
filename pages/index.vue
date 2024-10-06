<template>
    <div class="min-h-screen bg-gray-100 flex flex-col items-center justify-center">
      <!-- Hero Section -->
      <section class="text-center space-y-4">
        <h1 class="text-4xl font-bold text-gray-800">Welcome to Our Website</h1>
        <p class="text-lg text-gray-600">
          We provide the best services for your business.
        </p>
        <div class="mt-6">
          <button class="px-6 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700">
            Get Started
          </button>
        </div>
      </section>
  
      <!-- Features Section -->
      <section class="mt-16 w-full max-w-4xl text-center space-y-12">
        <h2 class="text-3xl font-semibold text-gray-800">Our Features</h2>
  
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <!-- Feature 1 -->
          <div class="bg-white shadow-lg rounded-lg p-6 space-y-4">
            <div class="text-blue-600">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
                class="w-12 h-12 mx-auto"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M3 15a4 4 0 010-8 4 4 0 014 4m5 0a4 4 0 014 4m0 0a4 4 0 00-4-4m4 4a4 4 0 01-4-4M21 13a4 4 0 100-8 4 4 0 00-4 4m0 0a4 4 0 004 4"
                />
              </svg>
            </div>
            <h3 class="text-xl font-bold">Feature 1</h3>
            <p class="text-gray-600">Amazing feature description goes here.</p>
          </div>
  
          <!-- Feature 2 -->
          <div class="bg-white shadow-lg rounded-lg p-6 space-y-4">
            <div class="text-green-600">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
                class="w-12 h-12 mx-auto"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M12 8c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2s-2 .9-2 2v1c0 1.1.9 2 2 2zM12 16v6m0 0h4m-4 0H8"
                />
              </svg>
            </div>
            <h3 class="text-xl font-bold">Feature 2</h3>
            <p class="text-gray-600">Description for another awesome feature.</p>
          </div>
  
          <!-- Feature 3 -->
          <div class="bg-white shadow-lg rounded-lg p-6 space-y-4">
            <div class="text-red-600">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
                class="w-12 h-12 mx-auto"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M12 8c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2s-2 .9-2 2v1c0 1.1.9 2 2 2zM12 16v6m0 0h4m-4 0H8"
                />
              </svg>
            </div>
            <h3 class="text-xl font-bold">Feature 3</h3>
            <p class="text-gray-600">A brief description of this feature.</p>
          </div>
        </div>
      </section>
    </div>
  </template>
  
  <script setup>
  // No special JavaScript logic required for this simple home page
  </script>
  
  <style scoped>
  /* Optionally, add custom styles here */
  </style>
  