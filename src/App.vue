<script setup lang="ts">
import Done from './components/Done.vue'
import HeaderList from './components/Header.vue'
import NewTask from './components/NewTask.vue'
import List from './components/List.vue'
import Task from './components/Task.vue'
import { reactive } from 'vue';
import { idText } from 'typescript'


const todos = reactive([
    {
        id: 0,
        name: 'Create the best TODO application in the world',
        completed: false
    },
    {
        id: 1,
        name: 'Publish in github pages',
        completed: false
    }
])

function addTodo (name: string){
  todos.push({
    id: todos.length,
    name: name,
    completed: false
  });
}
function deleteTodo (id: number){
  const index = todos.findIndex(todo => todo.id = id)
  todos.splice(index, 1);
}
</script>
<template>
    <header>
        <HeaderList />
    </header>
    <main>
        <NewTask @add = "addTodo"/>
        <List :todos="todos" @delete="deleteTodo"/>
        <Task />
        <Done />
    </main>
</template>

<style scoped>
/* header {
  line-height: 1.5;
} */

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>