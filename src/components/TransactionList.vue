<script>
export default {
    data() {
        return {
            transactions: [
                { id: 1, text: "flower", amount: -19.99 },
                { id: 2, text: "salary", amount: 299.97 },
                { id: 3, text: "book", amount: -10 },
                { id: 4, text: "camera", amount: 150 },
            ],
        };
    },
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
            <button class="delete-btn">x</button>
        </li>
    </ul>
</template>

<style scoped></style>
