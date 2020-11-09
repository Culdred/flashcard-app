**[DRAFT][WIP]**

---

**Project Analysis**

**Intro**
Using flashcards to self-test helps you learn information, and also helps you to identify any weak spots you may have with the material.

**Goal/Objective**
The user will be able to create a deck of cards and to test the deck.
- **Creation**: the user will create a deck of flashcards. Each card has a front and a back with an image (optional) and some text. 
- **Test**: as default behaviour the user will look at the front of the card and guess what's on its back (it will be possible to opt for doing it in reverse, first back then front). After the guess he/she will check the back (or front if in reverse mode) of the card to see if the guess was correct. After turning the card the user will also be prompted to choose if the answer was correct/wrong. At the end of the test a final card will show the result.

---

**Future improvement ideas for the app**:
- add a third layer for the card: the hint,
- add data persistence through a backend + db,
- add user auth + user profile,
- add the possibility for the user to edit a deck
- add user statistics (i.e. after a test, the missed cards will be proposed more frequently).

---

**Architecture**

Front-end: Vuejs + Vuex

Back-end: ...

---

**Data structure**

```
deck {
    title: string,
    subjects: [],
    description: string,
    public: true/false,
    cards: [{}, {}, {}, ...,]
}
```

```
card {
    front: {
        text: string,
        image: string,
    }
    back: {
        text: string,
        image: string,
    }
}
```

---

**Vue components structure**

**Components and Logic**:
The app will be made of mainly **3 components**: `<App.vue>` the main component, `<Deck.vue>` the component with the list of this deck's cards, `<Card.vue>` the template for the insertion of a single card's data.

- `<App.vue>` the user will be able to create a new deck (create `new deck` button) or do a test with a created deck (`new test` button) if it exists

**New deck**
- `<Deck.vue>` the user will use a form (through <Card.vue> component) to create the first card, there is a button to `add a card` that will add another form
- `<Deck.vue>` while creating a card the user will be able to delete the created card though a `remove` button
- `<Card.vue>` the form will be made of 2 sides: the front side and a back side wich will both contain a `textarea` for text and an `input box` to insert a link to an image

**Test**
- `<App.vue>` starting the test, a random card will be shown on screen (as a default behaviour the front will be shown, the reverse test will be added later)
- `<App.vue>` after clicking on the front of the card, the back is shown and the user will be prompted to select if the answer was correct or wrong; in both cases the next card is shown until the end of the deck
- `<App.vue>` once the test is finished a basic statistic is shown: number of cards tested, number of correct answers + percentage on total, number of wrong answers + percentage on total

