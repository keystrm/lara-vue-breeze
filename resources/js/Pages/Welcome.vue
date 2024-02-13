<script setup>
import { Head, Link } from '@inertiajs/vue3';

defineProps({
    canLogin: {
        type: Boolean,
    },
    canRegister: {
        type: Boolean,
    },
    laravelVersion: {
        type: String,
        required: true,
    },
    phpVersion: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <Head title="Welcome" />

    <div class="min-h-screen  bg-gray-100 dark:bg-gray-900 flex flex-col items-center justify-center px-4 sm:px-6 lg:px-8 text-white">
        <div class="mb-8 animate-bounce">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-16 w-16 md:h-20 md:w-20 text-blue-500" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
          </svg>
        </div>

        <h1 class="text-3xl sm:text-4xl md:text-5xl font-bold mb-2 text-center">Welcome to Our Website</h1>
        <p class="text-md sm:text-lg md:text-xl mb-8 text-center">A minimalist landing page with cool animations.</p>

        <div class="flex flex-col sm:flex-row space-y-4 sm:space-y-0 sm:space-x-4">
            <Link
            :href="route('login')"
            class="px-6 py-3 bg-blue-500 rounded hover:bg-blue-600 transition duration-300 ease-in-out transform hover:-translate-y-1"
            >
            Log in
            </Link>

            <Link
            v-if="canRegister"
            :href="route('register')"
            class="px-6 py-3 bg-green-500 rounded hover:bg-green-600 transition duration-300 ease-in-out transform hover:-translate-y-1"
            >
            Register
            </Link>
        </div>
    </div>

</template>

<style scoped>
@keyframes bounce {
  0%, 100% {
    transform: translateY(-25%);
    animation-timing-function: cubic-bezier(0.8, 0, 1, 1);
  }
  50% {
    transform: translateY(0);
    animation-timing-function: cubic-bezier(0, 0, 0.2, 1);
  }
}
.animate-bounce {
  animation: bounce 1s infinite;
}
</style>
