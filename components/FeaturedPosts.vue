<template>
    <div class="mx-auto px-4 py-16 sm:max-w-xl md:max-w-full md:px-24 lg:max-w-screen-xl lg:px-8 lg:py-20">
        <div>
            <h2
                class="pb-7 text-4xl font-extrabold dark:text-gray-700 sm:mx-auto sm:max-w-sm lg:max-w-full lg:grid-cols-3">
                Featured Posts</h2>
        </div>
        <div class="grid gap-8 sm:mx-auto sm:max-w-sm lg:max-w-full lg:grid-cols-3">
            <div class="rounded border bg-white p-8 shadow-sm">
                <p class="mb-3 text-xs font-semibold uppercase tracking-wide">
                    <a href="/"
                        class="text-deep-purple-accent-400 hover:text-deep-purple-800 transition-colors duration-200"
                        aria-label="Category">FrontEnd, HTML, CSS, JavaScript</a>
                    <span class="text-gray-600">— 1 Feb 2020</span>
                </p>
                <NuxtLink to="/post1" aria-label="Article"
                    title="8 Skills you must have as a Front-End Developer in 2022"
                    class="hover:text-deep-purple-accent-400 mb-3 inline-block text-2xl font-bold leading-5 text-black transition-colors duration-200">
                    8 Skills you must have as a Front-End Developer in 2022
                </NuxtLink>
                <p class="mb-5 text-gray-700">HTML, CSS, and JavaScript are basic coding skills but what are some skills
                    that make you stand out?</p>
            </div>
            <div class="rounded border bg-white p-8 shadow-sm">
                <p class="mb-3 text-xs font-semibold uppercase tracking-wide">
                    <a href="/"
                        class="text-deep-purple-accent-400 hover:text-deep-purple-800 transition-colors duration-200"
                        aria-label="Category">VsCode</a>
                    <span class="text-gray-600">— 15 Nov 2020</span>
                </p>
                <NuxtLink to="/post2" aria-label="Article" title="10 Must-Have VSCode Extensions for Web Development"
                    class="hover:text-deep-purple-accent-400 mb-3 inline-block text-2xl font-bold leading-5 text-black transition-colors duration-200">
                    10
                    Must-Have VSCode Extensions for Web Development</NuxtLink>
                <p class="mb-5 text-gray-700">Install these powerful VSCode extensions to significantly improve your
                    productivity during web development.</p>
            </div>
            <div class="rounded border bg-white p-8 shadow-sm">
                <p class="mb-3 text-xs font-semibold uppercase tracking-wide">
                    <NuxtLink to="/post6"
                        class="text-deep-purple-accent-400 hover:text-deep-purple-800 transition-colors duration-200"
                        aria-label="Category">JavaScript, Frameworks, Express.js, Nest.js</NuxtLink>
                    <span class="text-gray-600">— 28 Dec 2020</span>
                </p>
                <a href="/" aria-label="Article" title="Why i love C++"
                    class="hover:text-deep-purple-accent-400 mb-3 inline-block text-2xl font-bold leading-5 text-black transition-colors duration-200">Express.js
                    vs Nest.js</a>
                <p class="mb-5 text-gray-700">Since Node.js was announced, the use of Javascript has increased in the
                    backend world...</p>
            </div>
        </div>
        <div class="pt-6 sm:mx-auto sm:max-w-sm lg:max-w-full lg:grid-cols-3">
            <div>
                <a href="/blog" aria-label="Author" title="Author"
                    class="hover:text-deep-purple-accent-400 font-semibold text-gray-800 transition-colors duration-200">Read
                    all posts...</a>
            </div>
        </div>
    </div>
</template>