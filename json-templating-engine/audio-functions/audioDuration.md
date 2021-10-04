---
layout: page
grand_parent: JSON Templating Engine
parent: Audio functions
title: audioDuration
---

# audioDuration

Returns duration of audio in seconds from file path in first argument.

Currently, only supports PCM WAV files in RIFF format.


## Arguments

 - path: A path to the audio file

## Example

```json
{
  "$template": {
    "test": "{{"{{audioDuration('resources/sounds/sound.wav')"}}}}"
  }
}
```
