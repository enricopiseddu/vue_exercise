<template>

    <div class="house">
        <h3>{{ house.title }} <i @click="$emit('delete-house', house.id)" class="fas fa-times"></i></h3>
        <p>Superficie {{ house.mq }} mq, {{ house.baths }} bagni</p>
        
    </div>
    </template>
    
    
    <script>
    
    export default {
        name: 'AppHouse',
        props: {
            house: Object
        },
        methods: {
            
        }
    }
    </script>
    
    <style>
        .fas {
            color:red
        }
    
        .house {
            background: #f4f4f4;
            margin: 10px;
            padding: 10px 20px;
        }
    
        
        .house h3{
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
    
    
    </style>