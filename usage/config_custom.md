# Podcastfy Advanced Configuration Guide

Podcastfy uses a `config.yaml` file to manage various settings and parameters. This guide explains each configuration option available in the file.

## Customizing the Conversation

See [conversation_custom.md](conversation_custom.md) for more details.

## Output Directories

- `transcripts`: "./data/transcripts"
  - Directory where generated transcripts are saved.
- `audio`: "./data/audio"
  - Directory where generated audio files are saved.

## Text-to-Speech (TTS) Settings

### ElevenLabs TTS

- `default_voices`:
  - `question`: "Chris"
    - Default voice for questions in the podcast.
  - `answer`: "Jessica"
    - Default voice for answers in the podcast.
- `model`: "eleven_multilingual_v2"
  - The ElevenLabs TTS model to use.

### OpenAI TTS

- `default_voices`:
  - `question`: "echo"
    - Default voice for questions using OpenAI TTS.
  - `answer`: "shimmer"
    - Default voice for answers using OpenAI TTS.
- `model`: "tts-1-hd"
  - The OpenAI TTS model to use.

### Edge TTS

- `default_voices`:
  - `question`: "en-US-JennyNeural"
    - Default voice for questions using Edge TTS.
  - `answer`: "en-US-EricNeural"
    - Default voice for answers using Edge TTS.

### General TTS Settings

- `audio_format`: "mp3"
  - Format of the generated audio files.
- `temp_audio_dir`: "data/audio/tmp/"
  - Temporary directory for audio processing.
- `ending_message`: "Tchau!"
  - Message to be appended at the end of the podcast.

## Content Generator

- `gemini_model`: "gemini-1.5-pro-latest"
  - The Gemini AI model used for content generation.
- `system_prompt_file`: "prompt.txt"
  - File containing the system prompt for content generation.
- `max_output_tokens`: 8192
  - Maximum number of tokens for the output generated by the AI model.
- `temperature`: 0
  - Controls randomness in the AI's output. 0 means deterministic responses.
- `langchain_tracing_v2`: true
  - Enables LangChain tracing for debugging and monitoring.

## Content Extractor

- `youtube_url_patterns`:
  - Patterns to identify YouTube URLs.
  - Current patterns: "youtube.com", "youtu.be"

## Website Extractor

- `markdown_cleaning`:
  - `remove_patterns`:
    - Patterns to remove from extracted markdown content.
    - Current patterns remove image links, hyperlinks, and URLs.

## YouTube Transcriber

- `remove_phrases`:
  - Phrases to remove from YouTube transcriptions.
  - Current phrase: "[music]"

## Logging

- `level`: "INFO"
  - Default logging level.
- `format`: "%(asctime)s - %(name)s - %(levelname)s - %(message)s"
  - Format string for log messages.

## Main Settings

- `default_tts_model`: "openai"
  - Default Text-to-Speech model to use when not specified.



## Website Extractor

- `markdown_cleaning`:
	- `remove_patterns`:
		- Additional patterns to remove from extracted markdown content:
		- '\[.*?\]': Remove square brackets and their contents
		- '\(.*?\)': Remove parentheses and their contents
		- '^\s*[-*]\s': Remove list item markers
		- '^\s*\d+\.\s': Remove numbered list markers
		- '^\s*#+': Remove markdown headers
- `unwanted_tags`:
	- HTML tags to be removed during extraction:
		- 'script', 'style', 'nav', 'footer', 'header', 'aside', 'noscript'
- `user_agent`: 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36'
	- User agent string to be used for web requests
- `timeout`: 10
	- Request timeout in seconds for web scraping


