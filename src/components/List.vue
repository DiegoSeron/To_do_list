<script setup lang = "ts">
import { ref } from 'vue';
const props = defineProps(['todos'])

// function onClick(id: number) {
// console.log(`click on task ${id}`);

const emits = defineEmits(['delete'])
const todo = ref('');

function onDelete() {
    console.log("delete task");

    emits("delete", todo)
    todo.value = '';
}
</script>
<template>
    <v-card v-for="todo in todos">
        <v-row>
            <v-col cols="2">
        <v-switch v-model="todo.completed" name="" id=""></v-switch>
    </v-col>
    <v-col cols="8">
        {{ todo.name }}
    </v-col>
    <v-col cols="2">
        <button @click="onDelete(todos.id)">X</button>
    </v-col>
    </v-row>
    </v-card>
</template>