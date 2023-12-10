<script setup>
import { ref } from "vue";
import { Head, Link } from "@inertiajs/vue3";

import Magnify from "vue-material-design-icons/Magnify.vue";
import HeartOutline from "vue-material-design-icons/HeartOutline.vue";
import ChevronLeft from "vue-material-design-icons/ChevronLeft.vue";
import AccountPlusOutline from "vue-material-design-icons/AccountPlusOutline.vue";

import MenuItem from "@/Components/MenuItem.vue";

let showCreatePost = ref(false);
</script>

<template>
    <div id="MainLayout" class="w-full h-screen">
        <div
            v-if="$page.url === '/'"
            id="TopNavHome"
            class="fixed z-30 md:hidden block w-full bg-white h-[61px] border-b border-b-gray-300"
        >
            <div class="flex items-center justify-between h-full">
                <Link href="/">
                    <img
                        class="w-[105px] ml-6 cursor-pointer"
                        src="/insta-logo.png"
                        alt="Instagram Logo"
                    />
                </Link>
                <div class="flex items-center w-[50%]">
                    <div
                        class="flex items-center w-full bg-gray-100 rounded-lg"
                    >
                        <Magnify class="pl-4" fillColor="#8e8e8e" :size="27" />
                        <input
                            type="text"
                            placeholder="Search"
                            class="bg-transparent w-full border-0 ring-0 focus:ring-0 placeholder-[#8e8e8e]"
                        />
                    </div>
                    <HeartOutline
                        class="pl-4 pr-3"
                        fillColor="#000"
                        :size="27"
                    />
                </div>
            </div>
        </div>
        <div
            v-if="$page.url !== '/'"
            id="TopNavUser"
            class="md:hidden fixed flex items-center justify-center z-30 w-full bg-white h-[61px] border-b border-b-gray-300"
        >
            <Link href="/" class="px-4">
                <ChevronLeft :size="30" class="cursor-poiter"
            /></Link>
            <div class="font-extrabold text-lg">NAME HERE</div>
            <AccountPlusOutline :size="30" class="cursore-pointer px-4" />
        </div>

        <div
            id="SideNav"
            class="fixed h-full bg-white xl:w-[280px] w-[80px] md:block hidden border-r border-r-gray-300"
        >
            <Link href="/">
                <img
                    src="/insta-logo-small.png"
                    class="xl:hidden block w-[25px] mt-10 ml-[25px] mb-10 cursor-pointer"
                />
                <img
                    src="/insta-logo.png"
                    class="xl:block hidden w-[120px] mt-10 ml-6 mb-10 cursor-pointer"
                />
            </Link>

            <div class="px-3">
                <Link href="/">
                    <MenuItem iconString="Home" class="mb-4" />
                </Link>
                <Link href="/">
                    <MenuItem iconString="Search" class="mb-4" />
                </Link>
                <Link href="/">
                    <MenuItem iconString="Explore" class="mb-4" />
                </Link>
                <Link href="/">
                    <MenuItem iconString="Message" class="mb-4" />
                </Link>
                <Link href="/">
                    <MenuItem iconString="Notification" class="mb-4" />
                </Link>
                <Link href="/">
                    <MenuItem iconString="Create" class="mb-4" />
                </Link>
                <Link href="/">
                    <MenuItem iconString="Profile" class="mb-4" />
                </Link>
                <Link href="/">
                    <MenuItem iconString="Log out" class="mb-4" />
                </Link>
            </div>
        </div>
        <div
            class="flex lg:justify-between bg-white h-full w-[100%-280px] xl:pl-[280px] lg:pl-[100px] overflow-auto"
        >
            <div
                class="mx-auto md:pt-6 pt-20"
                :class="
                    $page.url === '/' ? 'lg:w-8/12 w-full' : 'max-w-[1200px]'
                "
            >
                <main>
                    <slot></slot>
                </main>
            </div>
            <div
                v-if="$page.url === '/'"
                id="SuggestionsSection"
                class="lg:w-4/12 lg:block hidden text-black mt-10"
            >
                <Link
                    href="/"
                    class="flex items-center justify-between max-w-[300px]"
                >
                    <div class="flex items-center">
                        <img
                            class="rounded-full z-10 w[58px] h-[58px]"
                            src="https://picsum.photos/id/237/300/320"
                        />
                        <div class="pl-4">
                            <div class="text-black font-extrabold">
                                Name HEre
                            </div>
                            <div class="text-gray-500 font-extrabold text-sm">
                                Name Here
                            </div>
                        </div>
                        <button
                            class="text-blue-500 hover:text-gray-900 text-xs font-extrabold"
                        >
                            Switch
                        </button>
                    </div>
                </Link>
            </div>
        </div>
    </div>
</template>
