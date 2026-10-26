<script setup>
defineProps(['items', 'title']);
</script>

<template>
    <h1>{{ title }}</h1>
    <ul>
      <li v-for="item in items" :key="item.id" :class="{
        'has-text-danger': item.importance === 3,
        'has-text-warning': item.importance === 2,
        'has-text-success': item.importance === 1
      }">
        <label>
          {{ item.text }}
          <input type="checkbox" v-model="item.isDone">
        </label>
      </li>
    </ul>
</template>
