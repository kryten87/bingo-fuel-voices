# Bingo Fuel voices

Voice models for the spoken radio in Bingo Fuel, an air-war campaign game. The game downloads them itself
when a player first turns RADIO VOICE on, and checks each archive's sha256 before unpacking it.

Each release is a voice set. The game names the set it was built with, so a release is never changed once
published: a rebuilt or new voice goes in a new set.

## voices-v1

| Voice | Archive | Bytes | sha256 |
|---|---|---|---|
| kristin | `piper-en_US-kristin-medium-fp16.tar.gz` | 29213187 | `09304ffee4b634f1fb9af6f8cd7ed85fc2ccd6940eadfab9266a37ca4fa2bd94` |
| cori | `piper-en_GB-cori-medium-fp16.tar.gz` | 29222480 | `132dfb33096688ded62ef2b319fb13c1427942004b0e6ef84c4564d74be371bb` |
| john | `piper-en_US-john-medium-fp16.tar.gz` | 29221592 | `3e9ffa8dce3cad6040b95155e566771742dd32fa220270d640ff1ae153fecbd9` |

About 88 MB in all.

## What they are

Piper voices by Bryce Beattie (kristin, cori and john, medium quality), trained on public-domain LibriVox
recordings. They are converted to float16, with fixes so they load and run reliably in
[sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx).

Each archive holds one folder:

- the `.onnx` model;
- `tokens.txt`, the model's phoneme symbols;
- `MODEL_CARD`, the voice's card from piper-voices, naming its training data and licence;
- `SOURCE.txt`, the exact upstream file and revision it was converted from.

They contain no espeak-ng data. The game sends the voices phonemes it works out itself.

## Licence: public domain

Our float16 conversions and this repository are dedicated to the public domain under
[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) (see `LICENSE`). Use them for anything, with or
without credit.

The voices they are made from are public domain too. Credit for them goes to their sources:

- **The voices:** kristin, cori and john by [Bryce Beattie](https://brycebeattie.com/files/tts/), who releases them
  as public domain.
- **The recordings** they were trained on: volunteers' readings from [LibriVox](https://librivox.org), which are
  public domain.
- **Where we got them:** [rhasspy/piper-voices](https://huggingface.co/rhasspy/piper-voices), the voice
  collection for the [Piper](https://github.com/rhasspy/piper) text-to-speech system, tagged MIT. Each archive's
  `SOURCE.txt` names the exact file, revision and sha256 it was converted from, and `MODEL_CARD` is that voice's
  card from there.

The originals are available, unchanged, from both of those pages.
