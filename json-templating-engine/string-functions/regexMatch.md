---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: regexMatch
---

# regexMatch

Returns an array of matches. Each match is an array containing the submatches (groups) derived from the regular expression pattern. The first submatch in each array is always the complete match found in the target string. If no matches are found, the function returns an empty array.
## Arguments

- `string` - The string to match.
- `args` - The regular expression to match against.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be true",
    "test": "{{"{{='hello world'.regexMatch('^hello ')"}}}}"
  }
}
```
