<script setup>
import OfficeCard from '@/components/molecules/OfficeCard.vue';

import {ref, onMounted} from 'vue';
import axios from 'axios';

const offices = ref([]);

onMounted(async () => {
    try{
        const response = await axios.get('/api/offices');
        offices.value = response.data
    }catch(error){
        console.error('Error fetching jobs',error);
    }
})


</script>
<template>
    <section class="bg-my-white px-8 py-10">
        <div class="m-auto">
            <div class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-5 gap-6">
                <OfficeCard v-for="office in offices" :key="office.id" :details="office"/>
            </div>
    </div>

    </section>
</template>