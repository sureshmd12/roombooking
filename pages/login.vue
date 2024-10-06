<template>
    <div class="flex items-center justify-center min-h-screen bg-gray-100">
        <div class="w-full max-w-md bg-white rounded-lg shadow-lg p-8 space-y-6">
            <h2 class="text-3xl font-bold text-center text-gray-800">Login</h2>
            <form @submit.prevent="handleSubmit" class="space-y-4">
                <!-- Email Field -->
                <div>
                    <label for="email" class="block text-sm text-gray-700">Email</label>
                    <input
                        v-model="email"
                        type="email"
                        id="email"
                        class="w-full mt-1 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-400 focus:border-transparent px-4 py-2"
                        placeholder="Enter your email"
                        required
                    />
                </div>

                <!-- Password Field -->
                <div>
                    <label for="password" class="block text-sm text-gray-700">Password</label>
                    <input
                        v-model="password"
                        type="password"
                        id="password"
                        class="w-full mt-1 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-400 focus:border-transparent px-4 py-2"
                        placeholder="Enter your password"
                        required
                    />
                </div>

                <!-- Submit Button -->
                <div>
                    <button
                        type="submit"
                        class="w-full py-2 mt-4 bg-blue-600 hover:bg-blue-700 focus:ring-2 focus:ring-blue-400 text-white rounded-lg">
                        Login
                    </button>
                </div>
            </form>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

// Data for login form
const email = ref('')
const password = ref('')

// Handle login submit
const handleSubmit = () => {
    // Simple check (you would handle actual login logic here)
    if (email.value && password.value) {
        alert(`Login successful with email: ${email.value}`)
    } else {
        alert('Please fill out both fields.')
    }
}
</script>

<style scoped>
/* Optional: Add any custom styles here */
</style>
