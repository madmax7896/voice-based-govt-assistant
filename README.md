# Voice-Based Government Scheme Assistant

A voice-first intelligent assistant that helps users identify and apply for government welfare schemes using natural spoken language.
The system supports Hindi speech input, performs intent reasoning, maintains conversation memory, and responds using speech output.

This project demonstrates a full agentic AI system with planning, execution, memory, and error handling.

## Key Features

* Voice Input (Hindi) using Vosk

* Planner–Executor–Evaluator Architecture

* Multi-turn conversational memory

* Eligibility checking for government schemes

* Speech output (Text-to-Speech)

* Offline-first (except TTS)

* Rule-based + LLM-powered reasoning

## System Architecture

![Architecture](https://github.com/madmax7896/voice-based-govt-assistant/blob/main/arch.png)


## Core Components

1. Speech-to-Text (STT)

	* Uses Vosk

	* Offline, low-latency speech recognition

	* Supports Hindi language

2. Planner

	* Determines user intent

	* Produces structured intent for the executor

3. Executor

	* Applies business logic

	* Calls eligibility engine

	* Updates conversation memory

	* Handles contradictions and confirmations

4. Evaluator

	* Ensures consistency (e.g., prevents changing age without confirmation)

	* Guards against invalid transitions

5. Memory

	* Stores: Age, Income

	* Pending confirmation state

6. Eligibility Engine

	* Rule-based evaluation of government schemes:

 	* Example:

		Age ≥ 18, Income ≤ ₹2,00,000 → Eligible for PM Awas Yojana

## Installation & Setup
Install Dependencies

```
pip install -r requirements.txt
```

Install Ollama runtime(for LLM)

Download from:
```
https://ollama.com
```
and install it.

Then get the LLM model using terminal(We are using mistral here):
```
ollama pull mistral
```

Run jupyter notebook
```
jupyter notebook
```

Open the notebook and run all cells.

## Example Interaction
-> User: मुझे सरकारी योजना के लिए आवेदन करना है
-> Agent: आपकी उम्र क्या है?
-> User: पच्चीस
-> Agent: आपकी आय कितनी है?
-> User: दो लाख
-> Agent: आप प्रधानमंत्री आवास योजना के लिए पात्र हैं।
