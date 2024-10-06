<template>
    <div class="min-h-screen bg-gray-100 p-8">
        <!-- Header -->
        <div class="flex justify-between items-center mb-8">
            <h1 class="text-3xl font-bold">Room Booking System</h1>
        </div>

        <!-- Date Range Selector -->
        <div class="mb-8">
            <label class="block mb-2 text-sm font-medium">Start Date:</label>
            <input v-model="startDate" type="date" class="p-2 border border-gray-300 rounded-lg mr-4" />

            <label class="block mb-2 text-sm font-medium">End Date:</label>
            <input v-model="endDate" type="date" class="p-2 border border-gray-300 rounded-lg" />

            <button @click="filterBookings" class="ml-4 px-4 py-2 bg-red-600 text-white rounded-lg hover:bg-red-700">
                Filter
            </button>
        </div>

        <!-- Booking Table -->
        <div class="bg-white shadow-lg rounded-lg p-6">
            <table class="min-w-full text-left">
                <thead>
                    <tr>
                        <th class="px-4 py-2">ID</th>
                        <th class="px-4 py-2">Date</th>
                        <th class="px-4 py-2">User Name</th>
                        <th class="px-4 py-2">Action</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="(booking, index) in filteredBookings" :key="index" class="border-t">
                        <td class="px-4 py-2">{{ booking.id }}</td>
                        <td class="px-4 py-2">{{ booking.date }}</td>
                        <td class="px-4 py-2">{{ booking.user_name }}</td>
                        <td class="px-4 py-2">
                            <button @click="viewBooking(booking)"
                                class="px-4 py-1 bg-blue-600 text-white rounded hover:bg-blue-700">
                                View
                            </button>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- View Booking Popup -->
        <div v-if="showBookingPopup" class="fixed inset-0 bg-black bg-opacity-50 flex justify-center items-center">
            <div class="bg-white p-6 rounded-lg shadow-lg w-full max-w-md">
                <h2 class="text-2xl font-bold mb-4">Booking Details</h2>
                <p><strong>ID:</strong> {{ selectedBooking.id }}</p>
                <p><strong>Date:</strong> {{ selectedBooking.date }}</p>
                <p><strong>User Name:</strong> {{ selectedBooking.user_name }}</p>
                <div class="flex justify-end mt-4">
                    <button @click="closeBookingPopup"
                        class="px-4 py-2 bg-gray-600 text-white rounded-lg hover:bg-gray-700">
                        Close
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

const startDate = ref('')
const endDate = ref('')
const showBookingPopup = ref(false)
const selectedBooking = ref(null)

// Sample booking data
const bookings = ref([
    { id: 1, date: '2024-10-01', user_name: 'John Doe' },
    { id: 2, date: '2024-10-02', user_name: 'Jane Smith' },
    { id: 3, date: '2024-10-03', user_name: 'Alice Johnson' },
])

const filteredBookings = ref(bookings.value)

const filterBookings = () => {
    if (startDate.value && endDate.value) {
        filteredBookings.value = bookings.value.filter(booking =>
            booking.date >= startDate.value && booking.date <= endDate.value
        )
    } else {
        filteredBookings.value = bookings.value
    }
}

const viewBooking = (booking) => {
    selectedBooking.value = booking
    showBookingPopup.value = true
}

const closeBookingPopup = () => {
    showBookingPopup.value = false
}
</script>

<style scoped>
/* Optional: Add any custom styles here */
</style>