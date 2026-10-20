<script>
export default {
    methods: {
        sendMessage() {
            alert('Thank you for contacting us! Your message form has been submitted.')
        }
    }
}
</script>

<template>
    <div id="contact" class="mt-16 w-full bg-gray-50 dark:bg-gray-900 sm:mt-20 md:mt-24 lg:mt-30">
        <!-- Contact Header -->
        <div class="mx-auto max-w-7xl px-4 pt-12 text-center sm:px-6 sm:pt-16 lg:px-8">
            <h2 class="text-3xl font-bold text-gray-900 dark:text-gray-100 sm:text-4xl">
                Contact
            </h2>

            <p
                class="mx-auto max-w-2xl px-2 pb-6 pt-5 text-sm leading-relaxed text-gray-600 dark:text-gray-400 sm:pb-8 sm:pt-6 sm:text-base">
                Want to contact us? Choose an option below, and we'll be happy to
                show you how we can transform your home furniture shopping experience.
            </p>
        </div>

        <!-- Contact Content -->
        <div
            class="mx-auto grid w-full max-w-7xl grid-cols-1 gap-10 px-4 pb-12 pt-6 sm:px-6 sm:pb-16 md:grid-cols-2 md:gap-8 lg:gap-16 lg:px-8">
            <!-- Contact Information -->
            <div class="min-w-0">
                <h2 class="text-xl font-bold text-gray-900 dark:text-gray-100 sm:text-2xl">
                    Contact Us
                </h2>

                <p class="mb-6 mt-4 max-w-md text-sm leading-relaxed text-gray-600 dark:text-gray-400 sm:text-base">
                    Have something to say? We are here to help. Fill out the form,
                    send us an email, or give us a call.
                </p>

                <!-- Address -->
                <div
                    class="mt-6 flex items-start gap-3 break-words text-sm text-gray-600 dark:text-gray-400 sm:text-base">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor" class="mt-1 h-5 w-5 shrink-0">
                        <path stroke-linecap="round" stroke-linejoin="round"
                            d="M9 6.75V15m6-6v8.25m.503 3.498l4.875-2.437c.381-.19.622-.58.622-1.006V4.82c0-.836-.88-1.38-1.628-1.006l-3.869 1.934c-.317.159-.69.159-1.006 0L9.503 3.252a1.125 1.125 0 00-1.006 0L3.622 5.689C3.24 5.88 3 6.27 3 6.695V19.18c0 .836.88 1.38 1.628 1.006l3.869-1.934c.317-.159.69-.159 1.006 0l4.994 2.497c.317.158.69.158 1.006 0z" />
                    </svg>

                    <span>14th avenue glory road</span>
                </div>

                <!-- Email -->
                <div
                    class="mt-4 flex min-w-0 items-start gap-3 break-all text-sm text-gray-600 dark:text-gray-400 sm:text-base">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor" class="mt-1 h-5 w-5 shrink-0">
                        <path stroke-linecap="round" stroke-linejoin="round"
                            d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75" />
                    </svg>

                    <a href="mailto:modernfurniturefinds@gmail.com"
                        class="transition-colors hover:text-black dark:hover:text-white">
                        modernfurniturefinds@gmail.com
                    </a>
                </div>

                <!-- Phone -->
                <div class="mt-4 flex items-start gap-3 text-sm text-gray-600 dark:text-gray-400 sm:text-base">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor" class="mt-1 h-5 w-5 shrink-0">
                        <path stroke-linecap="round" stroke-linejoin="round"
                            d="M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 002.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-.282.376-.769.542-1.21.38a12.035 12.035 0 01-7.143-7.143c-.162-.441.004-.928.38-1.21l1.293-.97c.363-.271.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 00-1.091-.852H4.5A2.25 2.25 0 002.25 4.5v2.25z" />
                    </svg>

                    <a href="tel:11111111111" class="transition-colors hover:text-black dark:hover:text-white">
                        +51 11111111111
                    </a>
                </div>
            </div>

            <!-- Contact Form -->
            <div class="min-w-0">
                <form @submit.prevent="sendMessage">
                    <!-- Honeypot -->
                    <input type="checkbox" name="botcheck" class="hidden" tabindex="-1" autocomplete="off" />

                    <!-- Full Name -->
                    <div class="mb-5">
                        <label for="name" class="sr-only">Full Name</label>

                        <input id="name" type="text" placeholder="Full Name" autocomplete="name" required
                            class="w-full rounded-md border-2 border-gray-300 bg-white px-4 py-3 text-sm text-gray-900 outline-none transition placeholder:text-gray-500 focus:border-gray-600 focus:ring-4 focus:ring-gray-100 dark:border-gray-600 dark:bg-gray-900 dark:text-white dark:placeholder:text-gray-400 dark:focus:border-white dark:focus:ring-0 sm:text-base"
                            name="name" />
                    </div>

                    <!-- Email Address -->
                    <div class="mb-5">
                        <label for="email_address" class="sr-only">
                            Email Address
                        </label>

                        <input id="email_address" type="email" placeholder="Email Address" autocomplete="email" required
                            class="w-full rounded-md border-2 border-gray-300 bg-white px-4 py-3 text-sm text-gray-900 outline-none transition placeholder:text-gray-500 focus:border-gray-600 focus:ring-4 focus:ring-gray-100 dark:border-gray-600 dark:bg-gray-900 dark:text-white dark:placeholder:text-gray-400 dark:focus:border-white dark:focus:ring-0 sm:text-base"
                            name="email" />
                    </div>

                    <!-- Message -->
                    <div class="mb-5">
                        <label for="message" class="sr-only">
                            Your Message
                        </label>

                        <textarea id="message" name="message" placeholder="Your Message" rows="5" required
                            class="min-h-36 w-full resize-y rounded-md border-2 border-gray-300 bg-white px-4 py-3 text-sm text-gray-900 outline-none transition placeholder:text-gray-500 focus:border-gray-600 focus:ring-4 focus:ring-gray-100 dark:border-gray-600 dark:bg-gray-900 dark:text-white dark:placeholder:text-gray-400 dark:focus:border-white dark:focus:ring-0 sm:text-base"></textarea>
                    </div>

                    <!-- Submit Button -->
                    <button type="submit"
                        class="w-full rounded-md bg-gray-900 px-6 py-3 text-sm font-semibold text-white transition duration-300 hover:bg-gray-700 focus:outline-none focus:ring-4 focus:ring-gray-300 dark:bg-white dark:text-black dark:hover:bg-gray-200 sm:py-4 sm:text-base">
                        Send Message
                    </button>
                </form>
            </div>
        </div>
    </div>
</template>