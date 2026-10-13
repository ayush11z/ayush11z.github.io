---
layout: project
title: "Multimodal Conversation Tracker"
description: A real-time system that tracks a multi-person conversation with a robot — who's talking, what they said, and who to address next — fusing speech diarization, transcription, and active-speaker vision.
importance: 8
category: Research
stack: ["Voice AI", "Computer Vision", "pyannote.audio", "faster-whisper", "Deepgram", "PyTorch", "SpeechBrain", "WebSocket"]
github: https://github.com/ayush11z/multimodal-conversation-tracker
summary: >-
  A robot that wants to join a group conversation first needs to know who's talking, what they
  said, and who to address next, so this project builds that pipeline from the ground up.
  Diarization (pyannote.audio) and transcription (faster-whisper) are aligned into speaker-labeled
  utterances with overlap and interruption detection, feeding a per-speaker state tracker and a
  rule-based engagement policy that decides who the robot should address next. I extended it past
  audio-only: a pretrained active-speaker-detection model links each utterance to a face on
  screen, a live pipeline does real-time mic capture with voice enrollment over WebSocket, and a
  Deepgram streaming alternative trades local/offline for meaningfully higher accuracy. Along the
  way I tracked down and fixed real bugs — a blocking event-loop stall from synchronous face
  capture, and a silent JSON-serialization failure from a stray numpy bool — both verified against
  full live multi-speaker runs.
---

A robot sitting in on a group conversation needs more than a transcript — it needs to know who's talking, what they said, and who it should address next. This project builds that pipeline end to end: diarization and transcription aligned into speaker-labeled utterances, a per-speaker state tracker, and a rule-based policy that decides who to address, then extends it well past the original spec into active-speaker vision and true real-time operation.

---

#### 🎙️ Core Pipeline

- **Diarization + transcription**: Aligned **pyannote.audio** speaker diarization with **faster-whisper** transcription into a timestamped, speaker-labeled transcript, with overlap and interruption events detected at the diarization-turn level.
- **Speaker state tracking**: Built a per-speaker state tracker — utterance history, time since last spoke, and an arousal trend derived from pitch and RMS energy audio features.
- **Engagement policy**: Designed a rule-based policy that decides who the robot should address next (direct question > recent interruption > quietest speaker) and why.

---

#### 👁️ Active Speaker Vision

- **Audio-visual linking**: Extended diarization past audio-only by vendoring and patching **Light-ASD** (CVPR 2023) to link each utterance to a face on screen via active speaker detection, running on CPU/MPS instead of the original hardcoded CUDA.
- **Video-synced viewer**: Built a local web viewer that replays a processed recording in sync with actual video playback.

---

#### 🔴 Real-Time Pipeline

- **Live audio speaker ID**: Built a true real-time path — mic capture, voice enrollment, speaker matching via ECAPA-TDNN embeddings, and a WebSocket-pushed live dashboard.
- **Deepgram streaming alternative**: Added a cloud-based path using Deepgram's streaming API after measuring the local pipeline's real accuracy ceiling, verified to be meaningfully more accurate against known ground truth.
- **Live avatar capture**: Combined the Deepgram path with real active-speaker-detection-based face capture rather than a single-frame guess, fixing a confirmed wrong-face bug and, along the way, a blocking event-loop stall and a silent JSON-serialization failure caused by an unconverted numpy bool — both fixed and verified against full live multi-speaker runs with zero errors.

---

#### 🛠️ Tech Stack

Python, pyannote.audio, faster-whisper, Deepgram (Nova-3), SpeechBrain (ECAPA-TDNN), Light-ASD, PyTorch, librosa, WebSocket

---

#### 💡 Why It's Relevant

The honest, specific limitations this project documents — where diarization breaks down at interruption points, where a single-frame face capture can grab the wrong person, where a numpy bool silently killed an entire event stream — mattered more to building it well than any individual accuracy number. It pushed me to treat real-time multimodal systems as something to instrument, measure, and be upfront about, not just demo once and move on.
