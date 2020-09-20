# Character 

> Apple documentation: The Character type represents a character made up of one or more Unicode scalar values, grouped by a Unicode boundary algorithm. Generally, a > Character instance matches what the reader of a string will perceive as a single character. Strings are collections of Character instances, so the number of visible characters is generally the most natural way to count the length of a string.

```swift 
for char in "Alex" {
  if char.isLowercase {
    print("\(char) is a lower letter")
  }
}

/*
 l is a lower letter
 e is a lower letter
 x is a lower letter
*/
```

## Resources 

1. [Apple documentation - Character](https://developer.apple.com/documentation/foundation/character)


# CharacterSet

> Apple Documentation: A CharacterSet represents a set of Unicode-compliant characters. Foundation types use CharacterSet to group characters together for searching > operations, so that they can find any of a particular set of characters during a search.

```swift 
for char in "Alex".unicodeScalars {
  if CharacterSet.lowercaseLetters.contains(char) {
    print("\(char) is a lower letter")
  }
}
/*
 l is a lower letter
 e is a lower letter
 x is a lower letter
*/
```

## Resouruces 

1. [Apple documentation - CharacterSet](https://developer.apple.com/documentation/foundation/characterset)
2. [Unicode Character Categories](https://www.compart.com/en/unicode/category)
3. [NSHipster - CharacterSet](https://nshipster.com/characterset/)
