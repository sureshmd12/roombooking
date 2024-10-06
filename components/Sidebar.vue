<template>
    <aside class="w-64 bg-blue-800 text-white py-6 px-3 space-y-6">
        <h2 class="text-2xl font-bold">Dashboard</h2>
        <nav class="space-y-4">
            <NuxtLink to="/dashboard" class="block px-4 py-2 rounded-lg hover:bg-blue-700" activeClass="bg-blue-700"
                exact-active-class="bg-blue-600">
                Overview
            </NuxtLink>
            <NuxtLink to="/user-management" class="block px-4 py-2 rounded-lg hover:bg-blue-700"
                activeClass="bg-blue-700" exact-active-class="bg-blue-600">
                Users
            </NuxtLink>
            <NuxtLink to="/room-management" class="block px-4 py-2 rounded-lg hover:bg-blue-700"
                activeClass="bg-blue-700" exact-active-class="bg-blue-600">
                Rooms
            </NuxtLink>
        </nav>
    </aside>
</template>