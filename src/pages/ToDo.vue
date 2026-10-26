<script setup>
import { computed, ref } from 'vue';
import ItemList from '../components/ItemList.vue';
import { items } from '../items.js';
let newItem = ref('');
let newImportance = ref(2);

function add(){
  if(newItem.value.trim() !== '') {
    let id = Math.max(-1, ...items.value.map(item => item.id)) + 1;
    items.value.push({id, text: newItem.value.trim(), isDone: false, importance: newImportance.value});
  }
  newItem.value = '';
}

let sortedItems = computed(() => [...items.value].sort((a, b) => b.importance - a.importance));
let doneItems = computed(() => sortedItems.value.filter(item => item.isDone));
let toDoItems = computed(() => sortedItems.value.filter(item => !item.isDone));
</script>

<template>
  <div class="container content mt-3">
    <div class="field has-addons">
        <div class="control is-expanded">
            <input @keydown.enter="add" v-model="newItem" class="input" type="text" placeholder="New item" aria-label="New item">
        </div>
        <div class="control">
            <div class="select">
                <select v-model="newImportance" aria-label="Importance">
                    <option :value="3">High</option>
                    <option :value="2">Medium</option>
                    <option :value="1">Low</option>
                </select>
            </div>
        </div>
        <div class="control">
            <button @click="add" class="button is-info">
                Add
            </button>
        </div>
    </div>
    <ItemList :items="sortedItems" title="All Items"></ItemList>
    <ItemList :items="doneItems" title="Done Items"></ItemList>
    <ItemList :items="toDoItems" title="ToDo Items"></ItemList>
  </div>
</template>

<style></style>
