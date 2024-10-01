<script setup>
import { ref, defineProps, onMounted } from 'vue';


const props = defineProps({
    userDetail: Object,
});


</script>

<template>
    <div class="flex justify-center items-center bg-gray-100 mt-4 mb-4" v-if="userDetail">
      <div class="bg-my-green text-my-white p-6 rounded-lg shadow-md w-96">
        <table class="table-auto w-full">
          <tbody>
            <tr>
              <td class="pr-4">Username:</td>
              <td>{{ userDetail.username }}</td>
            </tr>
            <tr>
              <td class="pr-4">Name:</td>
              <td>{{ userDetail.name }}</td>
            </tr>
            <tr>
              <td class="pr-4">Surname:</td>
              <td>{{ userDetail.surname }}</td>
            </tr>
            <tr>
              <td class="pr-4">Email:</td>
              <td>{{ userDetail.mail }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
    <div v-else>
      Loading...
    </div>
  </template>
  