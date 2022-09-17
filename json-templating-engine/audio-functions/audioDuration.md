---
layout: page
grand_parent: JSON Templating Engine
parent: Audio functions
title: audioDuration
---

# audioDuration

Returns the duration of an audio file in seconds.
## Arguments

- `path` - The path to the audio file.

## Example

{
  "$template": {
    "test": "{{"{{audioDuration('resources/sounds/sound.wav')"}}}}"
  }
}
