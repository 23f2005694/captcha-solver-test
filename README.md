# Ethical CAPTCHA Lab — Generator & Verifier (with Test Solver)

MIT Licensed demo web app to generate and validate your own CAPTCHA-style challenges. It includes a built‑in “Auto‑solve” strictly for developer testing of your own challenges. It does not perform OCR and is not intended to bypass third‑party CAPTCHA systems.

## Overview

This is a self-contained web app that helps you:

- Generate CAPTCHA-like challenges (digits, alphanumeric, or simple math).
- Render them on a canvas with per-letter rotation, offsets, noise lines, dots, and subtle warps.
- Verify user input against the known answer (for demo purposes, client-side; use server-side verification in production).
- Provide optional audio prompts using your browser’s speech synthesis for accessibility.
- Use a built-in “Auto-solve” to fill the known answer during development/testing of your own flows.

Important ethics and usage note:

- This tool is only for challenges you own and control (e.g., for your application).
- It is not an OCR breaker and must not be used to bypass third‑party CAPTCHA protections.

## Setup

No build required. Everything runs in the browser.

1. Download the repository files (index.html and this README).
2. Open index.html in any modern browser.

Optional: Serve over a local web server for best results with audio API (speechSynthesis works from file:// in most browsers, but localhost is recommended).

## Usage

- Challenge type: Choose digits, alphanumeric, or math.
- Length: Choose 3–8 characters (not used in math mode).
- Difficulty: Controls noise, warp, and variation.

Workflow:

1. Click “New CAPTCHA” to generate a challenge.
2. Optionally “Speak” the challenge for accessibility (math is read as a question; other modes spell out chars).
3. Enter your answer and click “Verify”.
4. Developer testing:
   - “Auto-solve” fills the known answer (it does not perform OCR; it simply reveals the internally generated answer to help integration tests).
   - “Refresh Noise” regenerates the noise/warp without changing the underlying answer.

Production guidance:

- Always verify CAPTCHA server-side to prevent tampering.
- Rotate secrets and rate-limit attempts.
- Pair with behavioral checks and logging for defense-in-depth.
- Offer accessible alternatives (e.g., audio, logic questions).

## License

MIT License

Copyright (c) 2025 Your Name

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the “Software”), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.