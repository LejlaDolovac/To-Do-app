<template>
    <main id="newtodo">
         <h2> Please add an item </h2>
        <input   class="field" type="text" v-model="newTodo"> <br>
        <button class="btn" @click="addTodo">Add</button>
        <footer> </footer>
        </main>
</template>

<script>
export default {
    name:"NewTodo",
    data(){
        return {
            newTodo: ''
        }

    },
    methods: {
        addTodo(){
            let todo = {
                done: false,
                text: this.newTodo
            }
            this.$emit('newtodo', todo);
            this.newTodo = '';
            this.$emit('swipe', 0);
        },
    }
   
    }


</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Handlee|Raleway');

#newtodo{
    .btn{
    font-family: 'handly';
    width: 50%;
    padding: 12px 20px;
    margin: 8px 0;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 15px;
    box-sizing: border-box;
    font-size: 1.0rem;
    text-transform: uppercase;
    background-color: pink;
    outline: none;
    font-family: system-ui;

    }

    .text{
    font-family: 'handly';
    width: 40%;
    padding: 12px 20px;
    margin: 8px 0;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 15px;
    box-sizing: border-box;
    font-size: 1.0rem;
    text-transform: uppercase;
    background-color:white;
    outline: none;
    margin-top: 5rem;
    text-align: center;
    }

    .btn-text{
        color: white;
    }
    
    .field{
        height: 2rem;
        border-radius: 999rem;
        width: 14rem;
    }
   
    
}

</style>

