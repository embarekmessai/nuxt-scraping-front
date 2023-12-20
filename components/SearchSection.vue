<script setup lang="ts">
import { reactive } from 'vue'
import axios from 'axios';

type Form = {
    url: string | null
};

const form = reactive<Form>({
    url: null,
});




const submit = async () => {
    console.log(form.url);
    
        await axios.post('http://localhost:5000/api/v1/url', {url: form.url})
        .then((res) => {
            console.log(res.data);
        })
        .catch((error) => {
            console.log(error);
        })
}
    
</script>
<template>
    <section class="bg-gray-50 dark:bg-gray-900 mb-14 mt-10 flex items-start rounded">
        <div class="max-w-screen-xl px-4 mx-auto lg:px-12 w-full">

            <div class="relative bg-white w-full shadow-md dark:bg-gray-800 rounded-lg">
                <div class="flex items-center justify-between p-4 space-y-3 md:flex-row md:space-y-0 md:space-x-4">
                    <div class="w-full">
                        <form @submit.prevent="submit" class="flex flex-col sm:flex-row space-x-3 sm:items-center sm:justify-between"
                            action="#">
                            <label for="simple-search" class="sr-only">Enter l'url</label>
                            <div class="relative sm:w-full">
                                <div class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none">
                                    <svg aria-hidden="true" class="w-5 h-5 text-gray-500 dark:text-gray-400"
                                        fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                                        <path fill-rule="evenodd"
                                            d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z"
                                            clip-rule="evenodd" />
                                    </svg>
                                </div>
                                <input type="text" id="inputUrl" v-model="form.url"
                                    class="block w-full p-2 pl-10 text-sm text-gray-900 border border-gray-300 rounded-lg bg-gray-50 focus:ring-primary-500 focus:border-primary-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                                    placeholder="Enter l'url: https//..." required />
                            </div>
                            <div
                                class="flex flex-col py-2 items-stretch justify-end flex-shrink-0 md:w-auto md:flex-row md:space-y-0 md:items-center md:space-x-3">
                                <button type="submit"
                                    class="flex items-center justify-center px-4 py-2 text-sm font-medium text-white rounded-lg bg-fuchsia-600 hover:bg-primary-800 focus:ring-4 focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 focus:outline-none dark:focus:ring-primary-800">
                                    <svg class="h-3.5 w-3.5 mr-2" fill="currentColor" viewBox="0 0 20 20"
                                        xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                                        <path clip-rule="evenodd" fill-rule="evenodd"
                                            d="M10 3a1 1 0 011 1v5h5a1 1 0 110 2h-5v5a1 1 0 11-2 0v-5H4a1 1 0 110-2h5V4a1 1 0 011-1z" />
                                    </svg>
                                    Créer le fichier produits
                                </button>

                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
