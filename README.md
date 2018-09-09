
# Gods Unchained Deckstrings

Deckstrings are a convenient format for encoding Gods Unchained decks so that they can be shared between third-party applications and the main game. 

Each deckstring is prefixed with a varint ```version```, encoded according to the google protobuf standard. 

## Version 1

All these fields are varints encoded according to the google protobuf standard.

First, the prefix is added:

```version|god|```

Where the god is the varint encoding of the name represented according to the following table:

| Name        | Representation        | 
| :-------------: |:-------------:| 
| ```nature``` | 1 |
| ```war``` | 2 |
| ```death``` | 3 |
| ```light``` | 4 |
| ```magic``` | 5 |
| ```deception``` | 6 |

Then, the cards are grouped together into frequency brackets as follows:

```
frequency|length|[protos]
```

For instance, a deck with protos: [1, 1, 2, 3] would be represented as two frequency brackets:

```1|2|[2, 3]``` and ```2|1[2]```
