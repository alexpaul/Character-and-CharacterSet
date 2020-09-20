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

1. [Apple Documentation - CharacterSet](https://developer.apple.com/documentation/foundation/characterset)
2. [Unicode Character Categories](https://www.compart.com/en/unicode/category)
3. [NSHipster - CharacterSet](https://nshipster.com/characterset/)
