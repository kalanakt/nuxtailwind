<template>
    <footer class="z-20 p-4 shadow md:flex md:items-center md:justify-between md:p-6 bg-transparent px-10">
        <span class="text-sm text-gray-500 sm:text-center dark:text-gray-400">© 2022 <a
                href="https://github.com/kalanakt" class="hover:underline">Kalanakt™</a>. All Rights Reserved.
        </span>
        <ul class="flex flex-wrap items-center mt-3 text-sm text-gray-500 dark:text-gray-400 sm:mt-0">
            <li class="pr-4 hover:underline md:mr-6 ">
                <NuxtLink to="/about">About</NuxtLink>
            </li>
            <li class="pr-4 hover:underline md:mr-6 ">
                <NuxtLink to="/privacypolicy">Privacy Policy</NuxtLink>
            </li>
            <li class="pr-4 hover:underline md:mr-6">
                <a href="/">Licensing</a>
            </li>
            <li class="pr-4 hover:underline md:mr-6">
                <NuxtLink to="/contact">Contact</NuxtLink>
            </li>
        </ul>
    </footer>
</template>