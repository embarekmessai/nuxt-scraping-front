<script setup lang="ts">

const props = defineProps({
    url: String
})

</script>

<template>
    <section class="flex flex-col items-center pb-10 hidden">
        <div class="w-full max-w-sm bg-white border pt-5 border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
            <div class="flex flex-col items-center pb-10">
                <img class="w-24 h-24 mb-3 rounded-full shadow-lg" src="https://icon-library.com/images/image-file-icon/image-file-icon-3.jpg" alt="Bonnie image"/>
                <h5 class="mb-1 text-xl font-medium text-gray-900 dark:text-white">Votre fichier est prêt!</h5>
                <span class="text-sm text-gray-500 dark:text-gray-400">Cliquez sur le button pour télécharger</span>
                <div class="flex mt-4 md:mt-6">
                    <a href="#" class="inline-flex items-center px-4 py-2 text-sm font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">Téléchager</a>
                </div>
            </div>
        </div>
    </section>
</template>