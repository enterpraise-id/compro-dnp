<script setup lang="ts">
import { defineEmits } from 'vue'
const emit = defineEmits(['prev', 'next'])
</script>

<template>
    <button class="top-1/2 pb-1 absolute left-6 h-10 w-10 text-white border white border-white " @click="$emit('prev')">&lt;</button>
    <button class="top-1/2 pb-1 absolute right-6 h-10 w-10 border text-gray-1 border-gray-1" @click="$emit('next')">&gt;</button>
</template>