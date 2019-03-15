<template>
    <article class="todo" :class="{ completed: todo.done }" v-touch:swipe.right="completed" >
        <aside class="done" v-if="todo.done">
            <img src="../assets/Vector.svg" alt="done">
        </aside>
        <section class="text">
            {{todo.text}}
        </section>
        
        </article>
</template>

<script>
export default {
    name: "todo",
    props: ['todo' , 'index'],
    methods: {
  completed(){
      console.log(this.index);

      this.$parent.$parent.todos[this.index].done = !this.$parent.$parent.todos[this.index].done;



  }
}

}



</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Handlee|Raleway');
.todo {
    background: #f246b3;
    padding: .25rem;
    display: flex;
    border-radius: 999rem;
    margin-top: 10px;
    height: 3rem;
    &.completed {
        .text {
           color: rgba(255, 168, 255, 0.9);
           text-decoration-line: line-through;     
    }
    }
    aside {
        background: #71ffaf;;
        width: 3rem;
        height: 3rem;
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 999rem;
    }
    .text {
        flex: 1;
        display: flex;
        align-items: center;
        padding: 0 0 0 1rem;
        color: white;
        text-transform: uppercase;
        font-family: 'Handly';
        font-size: 1.3rem;
    }
    img{
        display: flex;
        
    }
}
</style>
