<template>
    <div v-for="house in houses" :key="house.id">
       <House 
       @delete-house="$emit('delete-house', house.id)" :house="house" />
    </div>
</template>


<script>

import House from './House'

export default {
    name: 'AppHouses',
    props: {
        houses: Array
    },
    components:{
        House
    },
    methods: {
    },
    emits: ['delete-house'],
}
</script>
