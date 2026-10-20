# Basra

A two-player Basra card game in Python 3.14, with a graphical interface, computer opponents and an AI opponent.

Course project for "Python Development Practice" at MIPT.

## About the game

Basra (باصرة) is a card game popular in Arab countries.
It is a *fishing* game: you play cards from your hand to capture cards lying face up on the table,
either by matching their rank or by adding them up to your card's value.
You score points for winning the most cards, for a few special cards, and for every
*basra*, which means clearing the whole table with one capture.

## Rules

This game follows the classic Arab rules, for two players.

### Cards

- A standard 52-card deck without jokers.
- For adding up, an ace counts 1 and the cards 2–10 count their number.
  Jacks, queens and kings have no number value.

### The deal

1. The dealer deals 4 cards to each player and 4 cards face up to the table.
2. If a jack or the seven of diamonds (7♦) lands on the table, it goes back into the middle
   of the deck and is replaced by the top card of the deck, until the table has none.
3. The other player starts. Then the players take turns.
4. When both players have played all 4 cards, each gets 4 new cards.
   The table gets no new cards. One hand lasts 6 such rounds.
5. The dealer changes every hand.

### A turn

You play one card face up to the table. It either captures cards or stays on the table.

- **Matching:** a card captures every table card of the same rank.
- **Adding up:** a number card (ace to 10) also captures groups of number cards that add up to its value.
  Example: a 10 played on the table `10 4 6 Q` captures the 10, and the 4 and the 6 together, but not the queen.
- **Queen and king:** a queen captures only queens, and a king captures only kings.
- **Jack:** captures every card on the table. On an empty table it stays there.
- **Seven of diamonds (7♦):** captures every card on the table. On an empty table it stays there
  and later behaves like an ordinary 7.
- You may always play a card that captures nothing. But a card that can capture always does.
- Captured cards go to your pile, face down.

### Basra

A **basra** means your capture clears the whole table. It is worth **10 points**.

- A capture by a jack is never a basra.
- A capture by the seven of diamonds is a basra only when the table held number cards
  adding up to 10 or less. Otherwise it captures everything, but it is not a basra.

### End of a hand

When the deck is empty and the last cards are played, the cards still on the table go to the player
who made the last capture. This is not a basra.

### Scoring

| What | Points |
|---|---|
| Most cards (27 or more of the 52) | 30 |
| Each jack and each ace | 1 |
| Two of clubs (2♣) | 2 |
| Ten of diamonds (10♦) | 3 |
| Each basra | 10 |

If both players have 26 cards, nobody gets the 30 points. They carry over, so the most cards
in the next hand are worth 60.

The first player to reach **101 points** wins. If both reach it in the same hand, the higher score wins.
If the scores are equal, another hand is played.

### Rule choices in this version

Basra has many local variants. This game makes these choices:

- Two players only. The four-player version, played in pairs, is not included.
- A capturing card always takes **as many cards as it can**: every matching card and as many
  separate groups adding up to its value as possible. The game finds this capture for you.
- One game to 101 points. The best-of-five match from the full rules is not included.

## Game modes

- Player vs Player on one computer. Your cards are hidden while the other player moves.
- Player vs Computer, with three difficulty levels.
- Player vs AI: the opponent asks a language model which card to play.

## How to run

Instructions will be added with the first playable version. The game needs Python 3.14.

## Credits

- Rules: [Basra on pagat.com](https://www.pagat.com/fishing/basra.html), by John McLeod.
