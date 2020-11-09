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
