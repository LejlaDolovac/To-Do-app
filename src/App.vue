<template>
  <div id="app">
    <section class="slider" :class="'slide-' + activeSlide">
      <todos :todos="todos"  @swipe="handleSwipe"/>
      <newtodos  @swipe="handleSwipe"  @newtodo="newTodo" />
      </section>     
  </div>
</template>



<script>

import newtodos from './views/NewTodos.vue';
import todos from './views/todos.vue';


export default {
  name: 'app',
  data(){
    return {
      todos: [
        { done: false, text: 'buy bananas'},
        {done: false, text: 'buy milk'},
        {done: false, text: 'buy butter'},
        {done: false, text: 'buy bred'},
        {done: true, text: 'buy appels'}
      ],
      activeSlide: 0
    }
  },
  components: {
  todos,
  newtodos

},
methods: {
  handleSwipe(e){
    this.activeSlide = e;
  },
  newTodo(todo){
    this.todos.push(todo);
  }
}
}





</script>


<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Handlee|Raleway');

body {
  margin: 0;
  height: 100vh;
  background-color: bisque;

  #app {
    height: 100vh;
    text-align: center;
    overflow: hidden;

  .slider{
    width: 200vw;
    display: flex;
    height: inherit;
    overflow: hidden;
    transition: transform .2s ease;

    &.slide-0{
        transform: translate3d(0, 0, 0);
    }
    &.slide-1{
        transform: translate3d(-100vw, 0, 0);
    }
}
   
    main {
      flex: 1;

      .content{
        font-family: 'handly';
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;

        p{
        margin: 0;
        font-size: 1rem;
        font-family: 'handly';
        }
        
        h1{
        margin: 0;
        font-family: 'handly';
        }
        
      }

     
    }
}
  }



</style>
