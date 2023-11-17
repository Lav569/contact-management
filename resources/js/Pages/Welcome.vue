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
    <header class="bg-blue-500 text-white py-5 ">
        <h1 class="text-2xl mx-100">Contact Management App</h1>
    </header>
    <div >
        <div v-if="canLogin" class="sm:fixed sm:top-0 sm:right-0 p-6 text-right">
            <Link
                v-if="$page.props.auth.user"
                :href="route('dashboard')"
                class="font-semibold text-black-600 hover:text-black-900 dark:text-black-400 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                >Dashboard</Link>

            <template v-else>
                <Link
                    :href="route('login')"
                    class="font-semibold text-black-600 hover:text-black-900 dark:text-black-400 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                    >Log in</Link
                >

                <Link
                    v-if="canRegister"
                    :href="route('register')"
                    class="ml-4 font-semibold text-black-600 hover:text-black-900 dark:text-black-400 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                    >Register</Link
                >
            </template>
        </div>
        <div class="bg-gray-200 flex items-center justify-center h-screen">
         <div class="flex space-x-4">
            <div class="bg-white p-8 rounded-lg shadow-lg">
                <h1 class="text-2xl font-bold mb-6">Contact Management App Benefits</h1>
                <dl class="grid gap-4">
                    <div class="bg-white p-4 rounded-lg shadow">
                        <dt class="text-lg font-semibold">1. Centralized Contact Storage</dt>
                        <dd>Efficiently store and organize all your contacts in one central location.</dd>
                    </div>
                    <div class="bg-white p-4 rounded-lg shadow">
                        <dt class="text-lg font-semibold">2. Easy Accessibility</dt>
                        <dd>Access your contact information anytime, anywhere, and from any device.</dd>
                    </div>
                    <div class="bg-white p-4 rounded-lg shadow">
                        <dt class="text-lg font-semibold">3.Customizable Fields</dt>
                        <dd>Tailor contact entries with customizable fields to capture specific information relevant to your needs.</dd>
                    </div>
                    <div class="bg-white p-4 rounded-lg shadow">
                        <dt class="text-lg font-semibold">4. Contact Categorization</dt>
                         <dd>Organize contacts into categories or groups for easier management and segmentation.</dd>
                    </div>
                    <div class="bg-white p-4 rounded-lg shadow">
                        <dt class="text-lg font-semibold">5.Streamlined Communication</dt>
                        <dd>Facilitate streamlined communication by easily connecting with contacts through the app.</dd>
                    </div>
                </dl>
            </div>
            <div class="relative overflow-hidden">
                <img :src="'/logo.png'" class="" alt="logo">
            </div>
          </div>
        </div>
    </div>
</template>

<style>
</style>
