<template>
    <Head title="Users" />
    <div class="flex flex-col">
        <div
            class="shadow overflow-scroll border-b border-gray-200 sm:rounded-lg"
        >
            <table class="min-w-full divide-y divide-gray-200">
                <thead class="bg-gray-50">
                    <tr>
                        <th
                            scope="col"
                            class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
                        >
                            User
                        </th>
                        <th
                            scope="col"
                            class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
                        >
                            Status
                        </th>
                        <th scope="col" class="relative px-6 py-3">
                            <span class="sr-only">Edit</span>
                        </th>
                    </tr>
                </thead>
                <tbody v-if="users" class="bg-white divide-y divide-gray-200">
                    <tr v-for="user in users.data" :key="user.id">
                        <td class="px-6 py-4 whitespace-nowrap">
                            <div class="flex items-center">
                                <div class="flex-shrink-0 h-10 w-10">
                                    <span
                                        class="h-10 w-10 grid content-center justify-center bg-blue-300 rounded-full"
                                    >
                                        {{ user.name[0] }}
                                    </span>
                                </div>
                                <div class="ml-4">
                                    <div
                                        class="text-sm font-medium text-gray-900"
                                    >
                                        {{ user.name }}
                                    </div>
                                    <div class="text-sm text-gray-500">
                                        {{ user.email }}
                                    </div>
                                </div>
                            </div>
                        </td>
                        <td class="px-6 py-4 whitespace-nowrap">
                            <span
                                class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full"
                                :class="
                                    user.email_verified_at
                                        ? 'bg-green-100 text-green-800'
                                        : 'bg-gray-100 text-gray-800'
                                "
                            >
                                {{
                                    user.email_verified_at
                                        ? "Verified"
                                        : "Not verified"
                                }}
                            </span>
                        </td>
                        <td
                            class="px-6 py-4 whitespace-nowrap text-right text-sm font-medium"
                        >
                            <Link
                                href="#"
                                class="text-indigo-600 hover:text-indigo-900"
                            >
                                Edit
                            </Link>
                        </td>
                    </tr>

                    <!-- More people... -->
                </tbody>
                <tfoot>
                    <div class="flex space-x-3 p-3">
                        <Link
                            v-for="link in users.links"
                            :href="link.url"
                            :key="link"
                            v-html="link.label"
                            class="py-2 px-3 m-0.5 rounded border" 
                            :class="{'bg-blue-100': link.active}"
                            preserve-scroll
                        />
                    </div>
                </tfoot>
            </table>
        </div>
    </div>
</template>

<script setup>
import { Head } from "@inertiajs/inertia-vue3";
defineProps({
    users: Object,
});
</script>

<style></style>
