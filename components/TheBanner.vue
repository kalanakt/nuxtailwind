<template>
    <div>
        <div v-if="show" class="fixed bottom-0 left-0 ml-3 w-5/6 md:w-80">
            <div class="hover:bg-green-500 pointer-events-auto mx-auto mb-3 block w-96 max-w-full rounded-lg bg-green-400 bg-clip-padding text-sm shadow-lg"
                id="static-example" role="alert" aria-live="assertive" aria-atomic="true" data-mdb-autohide="false">
                <div class="flex items-center justify-between rounded-t-lg border-b bg-clip-padding py-2 px-3">
                    <p class="flex items-center font-bold text-white">
                        <svg class="mr-3 h-5 w-5 flex-shrink-0" xmlns="http://www.w3.org/2000/svg" data-name="Layer 1"
                            viewBox="0 0 24 24">
                            <path fill="#FFFF"
                                d="M12,2.2467A10.00042,10.00042,0,0,0,8.83752,21.73419c.5.08752.6875-.21247.6875-.475,0-.23749-.01251-1.025-.01251-1.86249C7,19.85919,6.35,18.78423,6.15,18.22173A3.636,3.636,0,0,0,5.125,16.8092c-.35-.1875-.85-.65-.01251-.66248A2.00117,2.00117,0,0,1,6.65,17.17169a2.13742,2.13742,0,0,0,2.91248.825A2.10376,2.10376,0,0,1,10.2,16.65923c-2.225-.25-4.55-1.11254-4.55-4.9375a3.89187,3.89187,0,0,1,1.025-2.6875,3.59373,3.59373,0,0,1,.1-2.65s.83747-.26251,2.75,1.025a9.42747,9.42747,0,0,1,5,0c1.91248-1.3,2.75-1.025,2.75-1.025a3.59323,3.59323,0,0,1,.1,2.65,3.869,3.869,0,0,1,1.025,2.6875c0,3.83747-2.33752,4.6875-4.5625,4.9375a2.36814,2.36814,0,0,1,.675,1.85c0,1.33752-.01251,2.41248-.01251,2.75,0,.26251.1875.575.6875.475A10.0053,10.0053,0,0,0,12,2.2467Z" />
                        </svg>
                        View On Github
                    </p>
                    <div class="flex items-center">
                        <p class="text-xs text-white opacity-90">1.1k stars</p>
                        <button @click="show = false" type="button"
                            class="-mx-1.5 -my-1.5 ml-auto inline-flex h-8 w-8 rounded-lg bg-transparent p-1.5"
                            data-dismiss-target="#alert-3" aria-label="Close">
                            <span class="sr-only">Close</span>
                            <svg aria-hidden="true" class="h-5 w-5" fill="currentColor" viewBox="0 0 20 20"
                                xmlns="http://www.w3.org/2000/svg">
                                <path fill="#FFFF" fill-rule="evenodd"
                                    d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                                    clip-rule="evenodd"></path>
                            </svg>
                        </button>
                    </div>
                </div>
                <div class="flex items-center">
                    <div class="break-words rounded-b-lg p-3 text-white">Give a Star & Follow me if you like.</div>
                    <div class="mx-1.5 ml-auto inline-flex h-8 w-8 rounded-lg bg-transparent p-1.5">
                        <a href="https://github.com/kalanakt/nuxt-blog">
                            <span class="sr-only">Link</span>
                            <svg stroke="#FFFF" class="h-5 w-5" viewBox="0 0 24 24" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path d="M13.5 10.5L21 3" stroke-width="2" stroke-linecap="round"
                                    stroke-linejoin="round" />
                                <path d="M16 3L21 3L21 8" stroke-width="2" stroke-linecap="round"
                                    stroke-linejoin="round" />
                                <path
                                    d="M21 14V19C21 20.1046 20.1046 21 19 21H12H5C3.89543 21 3 20.1046 3 19V5C3 3.89543 3.89543 3 5 3H10"
                                    stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
                            </svg>
                        </a>
                    </div>
                </div>
            </div>
        </div>
        <div v-else></div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

const show = ref(true)
</script>