# PROJECT C200 — Quiz Game

A multi-client TCP quiz game where a threaded socket server sends random general-knowledge questions to connected players and scores their answers.

## Features

- TCP socket server on 127.0.0.1:5000 accepting multiple clients via threads
- Nickname registration handshake (`NICKNAME` protocol)
- 17 built-in general-knowledge multiple-choice questions with answers
- Random question selection with automatic removal after each answer so questions are not repeated
- Per-player live scoring with immediate right/wrong feedback
- Concurrent receive/transmit threads in the client

## Tech Stack

- Python 3 (standard library only)
- `socket` for networking
- `threading` for concurrent clients

## Project Structure

```text
PROJECT-C200-main/
├── server.py       # Quiz server: accepts clients, asks questions, scores
└── quiz_client.py  # Terminal client: nickname prompt, receive/send threads
```

## Installation

No third-party dependencies. Requires Python 3.

```bash
python3 --version   # confirm Python 3 is available
```

## Usage

Start the server first:

```bash
python3 server.py
```

Then, in one or more separate terminals, launch clients:

```bash
python3 quiz_client.py
```

Type a nickname when prompted. Answer each question with `a`, `b`, `c`, or `d`; the server responds with your updated score.
