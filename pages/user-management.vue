<template>
    <div class="min-h-screen bg-gray-100 p-8">
        <!-- Header -->
        <div class="flex justify-between items-center mb-8">
            <h1 class="text-3xl font-bold">User Management</h1>
            <button @click="openCreatePopup" class="px-4 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700">
                Create User
            </button>
        </div>

        <!-- User Table -->
        <div class="bg-white shadow-lg rounded-lg p-6">
            <table class="min-w-full text-left">
                <thead>
                    <tr>
                        <th class="px-4 py-2">Name</th>
                        <th class="px-4 py-2">Email</th>
                        <th class="px-4 py-2">Actions</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="(user, index) in users" :key="index" class="border-t">
                        <td class="px-4 py-2">{{ user.name }}</td>
                        <td class="px-4 py-2">{{ user.email }}</td>
                        <td class="px-4 py-2">
                            <button @click="openEditPopup(user)"
                                class="mr-2 px-4 py-1 bg-green-600 text-white rounded hover:bg-green-700">
                                Edit
                            </button>
                            <button @click="confirmDelete(user)"
                                class="px-4 py-1 bg-red-600 text-white rounded hover:bg-red-700">
                                Delete
                            </button>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- Create/Edit Popup -->
        <div v-if="showPopup" class="fixed inset-0 bg-black bg-opacity-50 flex justify-center items-center">
            <div class="bg-white p-6 rounded-lg shadow-lg w-full max-w-md">
                <h2 class="text-2xl font-bold mb-4">{{ isEditMode ? 'Edit User' : 'Create User' }}</h2>
                <div class="mb-4">
                    <label class="block text-sm font-medium mb-2">Name</label>
                    <input v-model="form.name" type="text" class="w-full p-2 border border-gray-300 rounded-lg">
                </div>
                <div class="mb-4">
                    <label class="block text-sm font-medium mb-2">Email</label>
                    <input v-model="form.email" type="email" class="w-full p-2 border border-gray-300 rounded-lg">
                </div>
                <div class="flex justify-end">
                    <button @click="closePopup"
                        class="px-4 py-2 bg-gray-600 text-white rounded-lg hover:bg-gray-700 mr-2">Cancel</button>
                    <button @click="saveUser" class="px-4 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700">
                        {{ isEditMode ? 'Save Changes' : 'Create User' }}
                    </button>
                </div>
            </div>
        </div>

        <!-- Delete Confirmation Popup -->
        <div v-if="showDeletePopup" class="fixed inset-0 bg-black bg-opacity-50 flex justify-center items-center">
            <div class="bg-white p-6 rounded-lg shadow-lg w-full max-w-md">
                <h2 class="text-2xl font-bold mb-4">Confirm Delete</h2>
                <p>Are you sure you want to delete user <strong>{{ selectedUser.name }}</strong>?</p>
                <div class="flex justify-end mt-4">
                    <button @click="closeDeletePopup"
                        class="px-4 py-2 bg-gray-600 text-white rounded-lg hover:bg-gray-700 mr-2">
                        Cancel
                    </button>
                    <button @click="deleteUser" class="px-4 py-2 bg-red-600 text-white rounded-lg hover:bg-red-700">
                        Confirm
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
definePageMeta({
  layout: 'dashboard',
});
import { ref } from 'vue'

const users = ref([
    { name: 'John Doe', email: 'john@example.com' },
    { name: 'Jane Smith', email: 'jane@example.com' },
])

const showPopup = ref(false)
const showDeletePopup = ref(false)
const isEditMode = ref(false)
const form = ref({ name: '', email: '' })
const selectedUser = ref(null)

const openCreatePopup = () => {
    isEditMode.value = false
    form.value = { name: '', email: '' }
    showPopup.value = true
}

const openEditPopup = (user) => {
    isEditMode.value = true
    form.value = { ...user }
    showPopup.value = true
}

const closePopup = () => {
    showPopup.value = false
}

const saveUser = () => {
    if (isEditMode.value) {
        const index = users.value.findIndex((u) => u.email === form.value.email)
        users.value[index] = { ...form.value }
    } else {
        users.value.push({ ...form.value })
    }
    closePopup()
}

const confirmDelete = (user) => {
    selectedUser.value = user
    showDeletePopup.value = true
}

const closeDeletePopup = () => {
    showDeletePopup.value = false
}

const deleteUser = () => {
    users.value = users.value.filter((user) => user !== selectedUser.value)
    closeDeletePopup()
}
</script>

<style scoped>
/* Optional: Add any custom styles here */
</style>