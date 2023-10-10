<template>
    <form @submit="onSubmit" class="add-form">
        <div class="form-control">
            <label>Titolo</label>
            <input type="text" name="title" v-model="title"
            placeholder="Es. Casa campidanese" />
        </div>

        <div class="form-control">
            <label>Superficie</label>
            <input type="number" name="mq" v-model="mq"
            placeholder="es. 150mq" />
        </div>


        <div class="form-control">
            <label>Bagni</label>
            <input type="number" name="baths" v-model="baths"
            placeholder="es. 3" />
        </div>

        <input type="submit" value="Salva"
        class="btn btn-block" />
        </form>
</template>


<script>

export default {
    name: 'AddHouse',
    data(){
        return {
            title: '', //v-model in template
            mq: 0,
            baths: 0
        }
    },
    methods: {
        onSubmit(e){
            e.preventDefault()

            if(!this.title){
                alert('Please add a title')
                return
            }

            const newHouse ={
                id: Math.floor(Math.random()*100000),
                title: this.title,
                mq: this.mq,
                baths: this.baths
            }
            
            this.$emit('add-house', newHouse);

            

            console.log(newHouse)

            alert('House named ' + newHouse.title + ' correctly added')

            //clear the form
            this.title= '';
            this.mq= 0;
            this.baths= 0;
            

        }
    }
}
</script>


<style scoped>
    .add-form{
        margin-bottom: 40px;
    }

    .form-control {
        margin: 20px 0;
    }

    .form-control label {
        display: block;
    }

    .form-control input {
        width: 100%;
        height: 40px;
        margin: 5px;
        padding: 3px 7px;
        font-size: 17px;
    }

    
</style>
