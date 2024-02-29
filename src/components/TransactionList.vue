<script setup>
import { defineProps } from "vue";

const props = defineProps({
    transactions: {
        type: Array,
        required: true,
    },
});
</script>

<template>
    <h3>History</h3>
    <ul id="list" class="list">
        <li
            v-for="item in transactions"
            :key="item.id"
            :class="item.amount < 0 ? 'minus' : 'plus'"
        >
            {{ item.text }} <span>${{ item.amount }}</span>
            <button class="delete-btn">x</button>
        </li>
    </ul>
</template>

<style scoped></style>
