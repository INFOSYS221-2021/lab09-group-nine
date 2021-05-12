# Week 9 lab 9 
<p>
  
## Exercise One: Understand Deck of Cards
Go to the Deck of Cards API (Links to an external site.), read through the page, and answer the following questions.

### GET is one of the HTTP request methods. What is a GET method? Give an example of how you can use GET with the Deck Of Cards API.
A GET method is you asking the server for a payload or a response back from the server.
in this case you can use https://deckofcardsapi.com/api/deck/new/ with GET in the parameters to retrieve a json response 
```

{
    "success": true,
    "deck_id": "3p40paa87x90",
    "shuffled": false,
    "remaining": 52
}
```


### List all available features that you can use from Deck of Cards. For example, one of the APIs you can use is to shuffle cards.

- shuffle deck
- draw cards
- reshuffle
- get a brand new deck
- get a partial deck
- add to pile
- shuffle piles
- list cards in pile
- draw from pile

### What is the API for getting a brand new deck that also includes two jokers?

https://deckofcardsapi.com/api/deck/new/?jokers_enabled=true

### Looking at the following example response from the Deck of Cards API (Links to an external site.)
```{
    "success": true,
    "cards": [
        {
            "image": "https://deckofcardsapi.com/static/img/KH.png",
            "value": "KING",
            "suit": "HEARTS",
            "code": "KH"
        },
        {
            "image": "https://deckofcardsapi.com/static/img/8C.png",
            "value": "8",
            "suit": "CLUBS",
            "code": "8C"
        }
    ],
    "deck_id":"3p40paa87x90",
    "remaining": 50
}
```

#### How many cards are drawn from the deck? What are the cards? 
2 card are drawn, the King of Hearts and the 8 of Clubs

#### How do you retrieve deck_id from the response? Write your code using JavaScript.

```javascript
    mydeck = 
    {"success": true,
    "cards": [
        {
            "image": "https://deckofcardsapi.com/static/img/KH.png",
            "value": "KING",
            "suit": "HEARTS",
            "code": "KH"
        },
        {
            "image": "https://deckofcardsapi.com/static/img/8C.png",
            "value": "8",
            "suit": "CLUBS",
            "code": "8C"
        }
    ],
    "deck_id":"3p40paa87x90",
    "remaining": 50
}

console.log(mydeck.deck_id);
```

#### How do you print information about each card? Write your code using JavaScript.

```javascript
for (var card of mydeck.cards) {
    console.log(card.image)
    console.log(card.value)
    console.log(card.suit)
    console.log(card.code)
}
```
</p>

## Exercise Two: Complete Hit Me! Game with Deck of Cards API
### Follow the instructions below to complete the Hit Me! game. To test your code, please use CodePen (Links to an external site.) or JSFiddle (Links to an external site.). 

### 1. Open either  CodePen (Links to an external site.) or JSFiddle (Links to an external site.) and copy the following code snippet under the HTML section.
```
<h1>Hit Me!</h1>
<div>
  Try to get the total value of your cards closer to zero within 5 hits!
</div>
<h3>How to play</h3>
<div>
  <ul>
    <li>Click "Hit Me!" to get a card</li>
    <li>Each card has a value. Aces count as 1, Jacks count as 11, Queens count as 12, and Kings count as 13.</li>
    <li>Black cards are added to the total. Red cards are substracted from the total.</li>
    <li>You may take up to 5 hits</li>
  </ul>
</div>
<div>
  <input type="button" id="hitMeBtn" value="Hit Me!">
  <input type="button" id="restartBtn" value="Restart" disabled="disabled">
</div>
<hr />
<div id="hitMeSum">
  Click Hit Me! to start playing!
</div>
<div id="hitMeCards">

</div>
```
