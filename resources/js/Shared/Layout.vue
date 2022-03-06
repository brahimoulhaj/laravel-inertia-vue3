<template>
    <div class="flex">
        <div
            class="flex flex-col w-64 h-screen px-4 py-8 overflow-y-auto border-r"
        >
            <h2 class="text-3xl font-semibold text-center text-blue-800">
                Logo
            </h2>

            <div class="flex flex-col justify-between mt-6">
                <aside>
                    <ul>
                        <li>
                            <Link
                                class="flex items-center px-4 py-2 text-gray-700 rounded-md"
                                href="/"
                                :class="{ 'bg-gray-100': $page.url === '/' }"
                            >
                                <svg
                                    xmlns="http://www.w3.org/2000/svg"
                                    class="w-6 h-6"
                                    fill="none"
                                    viewBox="0 0 24 24"
                                    stroke="currentColor"
                                >
                                    <path
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                        stroke-width="2"
                                        d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"
                                    />
                                </svg>

                                <span class="mx-4 font-medium">Home</span>
                            </Link>
                        </li>

                        <li>
                            <Link
                                class="flex items-center px-4 py-2 mt-5 text-gray-600 rounded-md hover:bg-gray-200"
                                href="/users"
                                :class="{
                                    'bg-gray-100': $page.url === '/users',
                                }"
                            >
                                <svg
                                    xmlns="http://www.w3.org/2000/svg"
                                    class="h-6 w-6"
                                    fill="none"
                                    viewBox="0 0 24 24"
                                    stroke="currentColor"
                                    stroke-width="2"
                                >
                                    <path
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                        d="M12 4.354a4 4 0 110 5.292M15 21H3v-1a6 6 0 0112 0v1zm0 0h6v-1a6 6 0 00-9-5.197M13 7a4 4 0 11-8 0 4 4 0 018 0z"
                                    />
                                </svg>

                                <span class="mx-4 font-medium">Users</span>
                            </Link>
                        </li>
                    </ul>
                </aside>
            </div>
        </div>
        <div class="w-full h-full p-4 m-8 overflow-y-auto">
            <slot />
        </div>
    </div>
</template>
