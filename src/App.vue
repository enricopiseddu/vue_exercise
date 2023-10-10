<template>
  <div class="container">
    <Header msg="Immobiliare.it"/>

    <AddHouse @add-house="handleAddNewHouse" />

    <Houses @delete-house="handleDeleteHouse" :houses="houses"/>

  </div>
  
</template>

<script>
import Header from './components/Header.vue'
import Houses from './components/Houses.vue'
import AddHouse from './components/AddHouse.vue'


export default {
  name: 'App',
  components: {
    Header,
    Houses,
    AddHouse
  },
  data(){
    return {
      houses: []
    }
  },

  methods: {
    handleDeleteHouse(id){
      if(confirm("Are you sure to delete house "+ id + '?')){
        //console.log('house ', id, 'deleted')
        this.houses = this.houses.filter( (house) => house.id !== id )
      }
    },


    handleAddNewHouse(newHouse){

        this.houses.push(newHouse);

    }

  },



  created() {
    this.houses = [
        {
          id:1,
          title: 'Villetta a schiera',
          mq: 150,
          baths: 2,
        },
        {
            id:2,
            title: 'Appartamento a Sestu',
            mq: 75,
            baths: 1,
          },
          {
          id:3,
          title: 'Monolocale',
          mq: 35,
          baths: 1,
        },
        {
          id:4,
          title: 'Casa indipendente',
          mq: 220,
          baths: 3,
        }

    ]
  },
}




</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');

*{
  box-sizing: border-box;
  margin:0;
  padding: 0;
}

body {
  font-family: 'Poppins', sans-serif;
}

.container {
  background-color:bisque;
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}

.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}

.btn:focus {
  outline: none;
}

</style>