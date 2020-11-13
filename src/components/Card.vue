<template>
    <div>

        <h2>Card Component</h2>
        
        <form @click.prevent="addCard">
            <!-- Card's Front -->
            <h4>Front</h4>
            <div>
                <label for="frontText">Text</label>
                <input v-model="frontText" type="text" name="frontText" id="frontText" value="" placeholder="Insert some text...">
            </div>
            <div>
                <label for="frontImage">Image</label>
                <input v-model="frontImage" type="text" name="frontImage" id="frontImage" value="" placeholder="Insert an image url...">
            </div>
            <!-- Card's Back -->
            <h4>Back</h4>
            <div>
                <label for="backText">Text</label>
                <input v-model="backText" type="text" name="backText" id="backText" value="" placeholder="Insert some text...">
            </div>
            <div>
                <label for="backImage">Image</label>
                <input v-model="backImage" type="text" name="backImage" id="backImage" value="" placeholder="Insert an image url...">
            </div>
            <button type="submit">Add Card</button>
        </form>
    
        <ul>
            <li v-for="(card, idx) in deck" :key="idx">
                <div>{{ card.frontText }}</div>
                <div>{{ card.frontImage }}</div>
                <div>{{ card.backText }}</div>
                <div>{{ card.backImage }}</div>
            </li>
        </ul>
    
    </div>
</template>

<script>
export default {
    name: "Card",
    data: function() {
        return {
            card: {
                frontText: "",
                frontImage: "",
                backText: "",
                backImage: "",
            },
            deck: [],
        }
    },
    methods: {
        addCard(){
            this.deck.push({
                frontText: this.frontText,
                frontImage: this.frontImage,
                backText: this.backText,
                backImage: this.backImage,
            })
        },
    },
}
</script>