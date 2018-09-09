
# Gods Unchained Deckstrings

Deckstrings are a convenient format for encoding Gods Unchained decks so they can be shared between third-party applications and the main game. 

Deckstrings are base64 strings, prefixed with a protobuf varint ```version```. 

## Implementations

- [golang](https://github.com/fuelgames/go-deckstring)

## Version 1

The cards are grouped together into frequency brackets as follows:

```
frequency|length|[protos]
```

For instance, a deck with protos: [1, 1, 2, 3] would be represented as two frequency brackets: ```1|2|[2, 3]``` and ```2|1[2]```. 

The whole encoding, therefore, is:

```version|god|[frequency|length|[protos]]```

All numbers within these brackets (the frequency, the length and each of the protos) are encoded as protobuf varints. No other information is stored. 