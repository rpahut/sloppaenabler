# sloppaenabler
An automated frontend for the ElevenLabs text-to-dialogue API.

A simple, single page frontend for editing, generating and playing back dialogues using ElevenLabs text-to-dialogue API.
It is intended to convert YouTube chat messages containing dialogue into audio and play it back.
![](screenshot.jpg)
## Features
- A queue for dialogue texts
- Fuzzy characters name matching and automated parsing
- YouTubes user @handle extraction
- Audio noise detection and spectrogram visualisation
- Playback with speakers portraits
- Optional automatic queue advancement, generation and playback

Fully self-contained (no external dependencies).
## Setting up
### API Key
1. In the ElevenLabs console, navigate to Developers > API Keys. Create an API key with Text-To-Speech access.
2. Download the [SloppaEnabler.html](SloppaEnabler.html).
3. Open the .html file in a text editor, locate the 'API_KEY : ' line, and insert the key.
### Speakers/characters
To add a speaker, specify the voice ID from the ElevenLabs console. Provide one or more aliases (names) for it, separated with commas. Optionally, upload an image to use in the animation. Press 'Add/Replace' to save the speaker.

The first of the aliases determines the slot for the speaker to be recorded into. The existing speaker in the same slot, if any, will be replaced.
## Basic usage
Drop or type a dialogue text into the editor text field.

Press 'Generate' to submit the text for generation.

Once generation is complete and the generated audio is downloaded, press 'Play' to play it.

Alternatively, the text can be inserted into the queue first, and later accepted for editing and generation.
## Dialogue text expectations
> @author
>
> @streamer name1 : text name2 : text

or
> name1 : text name2 : text

So long as the body of the dialogue follows a general structure shown above, and reconiseable aliases are configured for the speakers, the code should be able to identify the parts correctly. The names will be matched regardless of capitalization and minor spelling mistakes.

If present, the first '@handle' at the beginning of the text will be used as the author name and displayed in the playback animation. Any @handles following it are ignored.

