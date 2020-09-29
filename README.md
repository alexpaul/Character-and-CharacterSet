# Character 

> Apple documentation: The Character type represents a character made up of one or more Unicode scalar values, grouped by a Unicode boundary algorithm. Generally, a > Character instance matches what the reader of a string will perceive as a single character. Strings are collections of Character instances, so the number of visible characters is generally the most natural way to count the length of a string.

#### `isLowercase`

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

#### `isCurrencySymbol`

```swift 
let amount = "$100"
let firstChar = amount.first ?? " "
if firstChar.isCurrencySymbol {
  print("valid currency")
} else {
  print("not a valid currency")
}
```

#### Many other `Character` checks available

```swift 
char.isASCII

char.isCased

char.asciiValue

char.isLetter

char.isMathSymbol

char.isWholeNumber

char.isWhitespace

char.isNumber

char.isLowercase

char.isNewline

char.isPunctuation
```

## Resources 

1. [Apple documentation - Character](https://developer.apple.com/documentation/foundation/character)


# CharacterSet

> Apple Documentation: A CharacterSet represents a set of Unicode-compliant characters. Foundation types use CharacterSet to group characters together for searching > operations, so that they can find any of a particular set of characters during a search.


## Built-in CharacterSets

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

## Building your own `CharacterSet`

#### Check if a String has vowels

```swift 
let vowels = CharacterSet(charactersIn: "aeiou")
let str = "alex"
if let _ = str.rangeOfCharacter(from: vowels) {
  print(true)
} else {
  print(false)
}
```

#### Check for symbol in String

```swift 
var happyMood = CharacterSet(charactersIn: "🥳🔥😀")
happyMood.insert(charactersIn: "😎")
happyMood.insert(charactersIn: "🎆")

let currentYear = "🎆😢😭🤬😱😤🤮"

for unicodeScalar in currentYear.unicodeScalars {
  if happyMood.contains(unicodeScalar) {
    print("\(unicodeScalar) happy")
  } else {
    print("\(unicodeScalar) sad")
  }
}
/*
🎆 happy
😢 sad
😭 sad
🤬 sad
😱 sad
😤 sad
🤮 sad
*/
```

## Useful use cases 

#### Removing puctuation 

```swift 
var sentence = "Swift is awesome! When are you joining the fun?"
sentence = sentence.components(separatedBy: .punctuationCharacters).joined()
print(sentence) // Swift is awesome When are you joining the fun
```

#### Removing symbols 

```swift 
var currentStatus = "🥳 Everything is awesome 🔥 🎆"
currentStatus = currentStatus.components(separatedBy: .symbols).joined()
print(currentStatus) // Everything is awesome
```

#### Validating data 

```swift 
var name = "Alex"
if CharacterSet(charactersIn: name).isSubset(of: CharacterSet.letters) {
  print("name comprises of only letters") // name comprises of only letters
} else {
  print("not a valid name")
}
```

```swift 
var password = "alex1234"
if CharacterSet(charactersIn: password).isSubset(of: CharacterSet.alphanumerics) {
  print("valid password created") // valid password created
} else {
  print("not a valid password")
}
```

## Challenges 

#### Challenge 1 - First unique character in a String

[LeetCode](https://leetcode.com/problems/first-unique-character-in-a-string/)

#### Challenge 2 - Find common characters

[LeetCode](https://leetcode.com/problems/find-common-characters/)

#### Challenge 3 - Shortest distance to a Character

[LeetCode](https://leetcode.com/problems/shortest-distance-to-a-character/)

#### Challenge 4 - Consecutive characters

[LeetCode](https://leetcode.com/problems/consecutive-characters/)


## Resouruces 

1. [Apple documentation - CharacterSet](https://developer.apple.com/documentation/foundation/characterset)
2. [Unicode Character Categories](https://www.compart.com/en/unicode/category)
3. [NSHipster - CharacterSet](https://nshipster.com/characterset/)
