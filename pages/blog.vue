<template>
    <div>
        <h1 class="py-3 px-10 text-3xl font-extrabold text-gray-800 capitalize lg:text-4xl">From the blog</h1>
        <div v-for="article of post" :key="article.slug" class="py-3 px-10 w-full lg:max-w-full lg:flex p-10">
            <div class="h-48 lg:h-auto lg:w-48 flex-none bg-cover rounded-t lg:rounded-t-none lg:rounded-l text-center overflow-hidden"
                :title="article.title">
                <img :src="article.img" :alt="article.title" width="200px" height="200px">
            </div>
            <div
                class=" bg-white rounded-b lg:rounded-b-none lg:rounded-r p-4 flex flex-col justify-between leading-normal">
                <div class="mb-8">
                    <p class="text-sm text-gray-600 flex items-center">
                        {{article.category}}
                    </p>
                    <div class="text-gray-900 font-bold text-xl mb-2">{{article.title}}</div>
                    <p class="text-gray-700 text-base">{{article.description}}</p>
                </div>
                <div class="flex items-center">
                    <p class="text-gray-600 pr-5">{{article.date}}</p>
                    <NuxtLink :to="article.slug" class="text-indigo-500 inline-flex items-center">Read More
                        <svg class="w-4 h-4 ml-2" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2" fill="none"
                            stroke-linecap="round" stroke-linejoin="round">
                            <path d="M5 12h14"></path>
                            <path d="M12 5l7 7-7 7"></path>
                        </svg>
                    </NuxtLink>
                </div>
            </div>
        </div>
    </div>
</template> 
  
<script>
export default {
    async asyncData({ $content }) {
        const post = await $content('post').fetch()
        return {
            post
        }
    }
}
</script>