<script setup>
import { ref } from 'vue';
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3';

// Mock data for demonstration purposes
const users = ref([
    { id: 1, name: 'John Doe', email: 'john@example.com' },
    { id: 2, name: 'Jane Doe', email: 'jane@example.com' },
]);

// Dummy functions to simulate CRUD operations
function addUser() {
    // Implement user addition logic
}

function updateUser(user) {
    // Implement user update logic
}

function deleteUser(userId) {
    // Implement user deletion logic
}
</script>

<template>
    <Head title="User Management" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 dark:text-gray-200 leading-tight">User Management</h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white dark:bg-gray-800 overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6">
                        <button
                            @click="addUser"
                            class="mb-4 px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-600">
                            Add User
                        </button>
                        <table class="w-full text-gray-900 dark:text-gray-100">
                            <thead>
                                <tr class="bg-gray-200 dark:bg-gray-700">
                                    <th class="px-6 py-3 text-left">Name</th>
                                    <th class="px-6 py-3 text-left">Email</th>
                                    <th class="px-6 py-3 text-right">Actions</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr v-for="user in users" :key="user.id" class="border-b">
                                    <td class="px-6 py-4">{{ user.name }}</td>
                                    <td class="px-6 py-4">{{ user.email }}</td>
                                    <td class="px-6 py-4 text-right">
                                        <button
                                            @click="updateUser(user)"
                                            class="px-4 py-2 bg-green-500 text-white rounded hover:bg-green-600 mr-2">
                                            Edit
                                        </button>
                                        <button
                                            @click="deleteUser(user.id)"
                                            class="px-4 py-2 bg-red-500 text-white rounded hover:bg-red-600">
                                            Delete
                                        </button>
                                    </td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
