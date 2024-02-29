<script setup>
const props = defineProps({
    transactions: {
        type: Array,
        required: true,
    },
});

const emit = defineEmits(["transactionDeleted"]);

const deleteTransaction = (id) => {
    emit("transactionDeleted", id);
};
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
            <button @click="deleteTransaction(item.id)" class="delete-btn">
                x
            </button>
        </li>
    </ul>
</template>

<style scoped></style>
