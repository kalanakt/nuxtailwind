<template>
    <div class="flex flex-col items-center justify-center overflow-hidden px-8 sm:px-12 py-2 sm:py-4">
        <div class="w-full max-w-4xl rounded-md border-2 border-gray-100 bg-white p-14">
            <div class="flex flex-col items-center">
                <span class="rounded-lg bg-yellow-100 py-px px-2 text-sm text-yellow-800">117+ people joined
                    this week</span>
                <h3
                    class="mt-2 max-w-2xl text-center text-2xl font-bold leading-tight sm:text-3xl md:text-4xl md:leading-tight">
                    Subscribe to the newsletter</h3>
                <p class="mt-2 max-w-2xl text-center font-bold leading-tight md:leading-tight">
                    Get emails from me about web development, tech, and early access to new articles.</p>
                <form action="" class="mx-auto mt-4 flex w-full max-w-md flex-col gap-3 sm:flex-row sm:gap-0">
                    <input id="email" type="email" name="email"
                        class="grow rounded border-2 border-gray-300 py-3 px-3 focus:border-emerald-500 focus:outline-none sm:rounded-l-md sm:rounded-r-none sm:border-r-0"
                        placeholder="Email Address" />
                    <button type="submit"
                        class="rounded bg-emerald-500 px-5 py-4 font-bold text-white sm:rounded-l-none sm:rounded-r-md">Get
                        First Email</button>
                </form>
            </div>
        </div>
    </div>
</template>