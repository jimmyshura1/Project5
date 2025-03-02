<script setup>
    import { faker } from '@faker-js/faker'
    const firstname = faker.person.firstName()
    const lastname = faker.person.lastName()
    const jobtitle = faker.person.jobTitle()
    const bio = faker.lorem.lines(2)
    const phone = faker.phone.number()
    const status = faker.lorem.sentence()
    const username = faker.internet.username({firstName: firstname, lastName: lastname}).toLowerCase()
</script>

<template>
    <RouterLink :to="{name: 'CardDetail', params: {id: username}}">
        <div class="border border-lime-400 rounded-lg shadow bg-gray-400 h-full">
            <img class="object-fill h-480 w-960 rounded-t-lg" v-bind:src="faker.image.urlLoremFlickr({category: 'birds', height: 480, width: 960})" />
            <div class="p-4">
                <p class="mb-2 text-2xl text-cyan-400 font-bold">{{ firstname }} {{ lastname }}</p>
                <p class="mb-3 font-normal text-green-600">{{ jobtitle }}</p>
                <p class="mb-3 font-normal text-purple-500">{{ bio }}</p>
                <p class="text-gray-500">{{ phone }}</p>
                <p class="text-gray-700 italic">“{{ status }}”</p>
            </div>
        </div>
    </RouterLink>
</template>