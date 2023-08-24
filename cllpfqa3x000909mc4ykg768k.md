---
title: "Split ,Reverse And Join String methods"
datePublished: Thu Aug 24 2023 17:25:49 GMT+0000 (Coordinated Universal Time)
cuid: cllpfqa3x000909mc4ykg768k
slug: split-reverse-and-join-string-methods
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/B3l0g6HLxr8/upload/13fad7726af5af91f6f0d334adcabf8d.jpeg
tags: javascript, hashnode, string, string-methods

---

# Split()

Split is a string method used to split a string into an array of substrings based on a specified delimiter.

which means the string will be split at each individual character. This effectively converts the string into an array of characters.

```xml
const str = "hello";
const arr = str.split('');
// arr is now ['h', 'e', 'l', 'l', 'o']
```

# Reverse()

The reverse method is an array method that reverses the order of elements in an array.

```xml
const arr = ['h', 'e', 'l', 'l', 'o'];
const reversedArr = arr.reverse();
// reversedArr is now ['o', 'l', 'l', 'e', 'h']
```

# Join()

The Join method is used to combine elements of an array into a single string, using a specified delimiter to separate the elements.

```xml
const reversedArr = ['o', 'l', 'l', 'e', 'h'];
const reversedStr = reversedArr.join('');
// reversedStr is now "olleh"
```

## Technical word with meaning

> `delimiter` - A delimiter is a character or sequence of characters used to separate or distinguish different parts of a text or data. It's commonly used in various contexts to define boundaries between elements, values, or tokens. Delimiters are crucial for parsing and processing data because they help identify where one piece of information ends and the next one begins.