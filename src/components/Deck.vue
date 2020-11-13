<template>
    <div>
        <h2>Deck Component</h2>
        <button @click="showDeckCreate = !showDeckCreate" type="button">
            Create New Deck
        </button>
        <form v-if="showDeckCreate">
            <Card />
        </form>
    </div>
</template>

<script>
import Card from "./Card.vue"

export default {
    name: "Deck",
    components: {
        Card,
    },
    data: () => ({
        showDeckCreate: false,
    }),
}
</script>