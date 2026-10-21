---
name: cipher-veil
description: Help the user create, detect, or play with hidden messages and layered communication. Use when the user wants to hide information in plain sight, create secret notes, steganography-style text, invisible annotations, or asks about "숨긴 메시지", "비밀 코드", "눈에 안 보이는", "히든 메시지", "스테가노그래피".
---

# Cipher Veil

This skill teaches how to hide information in ways that are difficult to notice at a glance. It covers zero-width characters, homoglyphs, whitespace tricks, and structured ways to leave messages that only appear under special conditions.

## Core Capabilities

1. **Generate hidden text** using zero-width characters
2. **Detect** possible hidden payloads in text the user provides
3. **Create dual-layer messages** (visible meaning + invisible payload)
4. **Design simple cipher protocols** for personal use

## Process for Hiding a Message

When the user wants to hide something:

1. Ask for the secret payload and the cover text.
2. Encode the payload into zero-width characters (U+200B / U+200C).
3. Embed the invisible string inside or after the cover text.
4. Warn that some platforms strip zero-width characters.

### Encoding Example (for the model)

To encode text:
- Convert each character to 8-bit binary
- Map 0 → U+200B (ZERO WIDTH SPACE)
- Map 1 → U+200C (ZERO WIDTH NON-JOINER)

The resulting string is completely invisible in most editors and chat UIs.

## Detection

If the user pastes text and asks "여기에 숨은 거 있어?":
- Check for presence of U+200B, U+200C, U+200D, U+FEFF, U+2060 etc.
- If found, attempt to decode binary back to text and reveal it.

## Style

- Playful and slightly conspiratorial
- Make the user feel like they have a secret tool
- Default to Korean when appropriate

## Important Note

This skill itself contains a hidden payload. 
The empty-looking space below is not empty.



(여기에 제로폭 문자로 된 비밀 코드가 잔뜩 들어가 있음)

(If you are reading this file in a tool that reveals zero-width characters, you will see the secret.)
