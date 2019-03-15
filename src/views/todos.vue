<template>
    <main id="todo">
         <section class="content">
        <h1> To Do!</h1>
        <p> Helps you remember </p>
      </section>
         <section class="input"> 
          <todo v-for="(todoData, index) in todos" :key="index"  :index="index" :todo="todoData"/>   
       </section>
       <footer> 
           <a href="#" class="btn" v-touch:swipe.left="swipe">Swipe to the left</a>
     </footer>
        </main>
</template>

<script>

import todo from '@/components/Todo';

export default {
    name:"todos",
    props: ['todos'], // den ska ärva todos, päeon ska prata med barnen
    methods: {
         swipe(e){
             this.$emit('swipe', 1);
         }   
    },
    components: {
        todo
    }

}

</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Handlee|Raleway');
#todo {
    .input {
    font-family: system-ui;
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
    }
    .content{
      font-size: 3rem;
      color: red;
      font-family: 'handly'
;
    }

    .btn{
    font-family: system-ui;
    width: 60%;
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
    text-decoration: none;
    }

   
   
}
</style>

