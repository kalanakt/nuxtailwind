<template>
  <div>
    <div class="basis-1/2">
      <NuxtContent class="prose prose-sm sm:prose lg:prose-lg xl:prose-2xl mx-auto" :document="poster" />
    </div>
    <div class="flex justify-center ">
      <div v-if="prev" class="ring ring-blue-300 hover:ring-blue-500 rounded-md p-4 m-3 mt-10">
        <NuxtLink :to="prev.slug"> {{ prev.title }} </NuxtLink>
      </div>
      <div v-if="next" class="ring ring-blue-300 hover:ring-blue-500 rounded-md p-4 m-3 mt-10">
        <NuxtLink :to="next.slug"> {{ next.title }} </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const poster = await $content('post', params.slug).fetch()
    const [prev, next] = await $content('post')
      .only(['title', 'slug'])
      .sortBy('createdAt', 'asc')
      .surround(params.slug)
      .fetch()
    return {
      poster,
      prev,
      next
    }
  }
}
</script> 
  