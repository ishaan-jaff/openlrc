# Open-Lyrics

Open-Lyrics is a Python library that transcribes voice files using
[faster-whisper](https://github.com/guillaumekln/faster-whisper), and translates/polishes the resulting text
into `.lrc` files in the desired language using [OpenAI-GPT](https://github.com/openai/openai-python).

**This new project is rapidly underway, and we welcome any issues or pull requests.**

## Installation

1. Please install CUDA and cuDNN first according to https://opennmt.net/CTranslate2/installation.html to
enable `faster-whisper`.

2. Add your [OpenAI API key](https://platform.openai.com/account/api-keys) to environment variable `OPENAI_API_KEY`.

3. This project can be installed from PyPI:

    ```shell
    pip install openlrc
    ```
   or install directly from GitHub:

    ```shell
    pip install git+https://github.com/zh-plus/Open-Lyrics
    ```

## Usage

```python
from openlrc import LRCer

lrcer = LRCer()
lrcer('./data/test.mp3', target_lang='zh-cn')  # Generate translated ./data/test.lrc with default translate prompt.
# lrcer('./data/test.mp3', prompter='lovely_trans')  # Generate ./data/test.lrc with lovely colloquial expressions.
```

## Todo

- [ ] Add transcribed examples.
    - [ ] Song
    - [ ] Podcast
    - [ ] Audiobook
- [ ] Make translate prompt more robust.
- [ ] Add local LLM support.
- [ ] Concurrent support for both whisper model and GPT request.
    - [ ] Whisper
    - [x] GPT
- [ ] Automatically fix json encoder error using GPT.

## Credits

- https://github.com/guillaumekln/faster-whisper
- https://github.com/openai/openai-python
- https://github.com/openai/whisper