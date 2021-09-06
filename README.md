```
grep -P to allow PCRE

```

Regular expressions are a series of characters that define patterns to search for in text. 

1. Basic Usage
   1. Single characters
      1. `A`
      2. `1`
      3. `\t`
   2. Multiple characters
      1. `[abc]`
      2. `[157]`
   3. Ranges
      1. `[a-z]`
      2. `[A-Z]`
      3. `[a-zA-Z]`
   4. Any character except line terminators
      1. `.`
   5. NOT
      1. `How would I match consonants?`
         1. `[b-df-hj-np-tv-z]` vs `[^aeiou] `
      2. `[^2-8]`
   6. Escaping characters
      1. `\.`
      1. `\[`
2. Meta-sequences
   1. `\s and \S    whitespace`
   2. `\d and \D    digits`
   3. `\w and \W    word characters [a-zA-Z1-9_]`
* Phone number checker WITHOUT quantifiers 
    * Form to match: `123-456-7890`
    * <details>
      <summary>Answer!</summary>

        `\d\d\d-\d\d\d-\d\d\d\d`
      </details>
3. Quantifiers (remember they need to go outside the brackets)
    1. `?     Zero or one`
    2. `*     Zero or more`
    3. `+     One or more`
    4. `{3}   Exactly 3`
    5. `{3,}  3 or more`
    5. `{,3}  At most 3, zero included`
    7. `{3,6} Between 3-6 times, inclusive`
* Phone number checker WITH quantifiers 
    * Form to match: `123-456-7890`
    * <details>
      <summary>Answer!</summary>

        `\d{3}-\d{3}-\d{4}`
      </details>
    * Form to match: Same but with optional US country code at beginning `1123-456-7890`
    * <details>
      <summary>Answer!</summary>

        `1?\d{3}-\d{3}-\d{4}`
      </details>
4. Anchors
    1. `^`     Beginning of line
    2. `$`     End of line
5. Groups
   1. So far you could only quantify single characters at a time. You can quantify whole groups.
      1. `[123]+ vs (123)+` 
