<script setup lang="ts">
import { ref } from 'vue';

const emits = defineEmits(['add'])
const name = ref('');

function onAdd() {
    emits("add", name.value)
    name.value = '';
}

</script>

<template>
    <!-- <v-row> -->
        <v-text-field v-model="name" label="Task name" hide-details="auto" type="text" name="" id=""></v-text-field>
        <!-- <button @click="onAdd">Add</button> -->
        <v-btn variant="outlined" @click="onAdd">ADD TASK</v-btn>
    <!-- </v-row> -->
</template>