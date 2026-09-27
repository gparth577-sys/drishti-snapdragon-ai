# Drishti — Offline On-Device AI Accessibility Companion

**Snapdragon® AI Lab Build & Present Challenge — Submission by Parth Gupta**

Drishti is a fully offline, real-time AI assistant that helps visually impaired
users read, navigate, and understand their surroundings — running entirely
on-device on the Hexagon NPU of a Snapdragon-powered HP PC.

## Problem

India has 25M+ people who are visually impaired or have low vision. Existing
tools (Seeing AI, Be My Eyes) require constant internet connectivity, stream
live camera feed to the cloud, and introduce latency that's unacceptable for
real-time obstacle warnings — while also raising serious privacy concerns.

## Solution

Drishti runs four capabilities fully offline:
- **Reads aloud** — OCR on documents, signs, and labels
- **Describes the scene** — narrates surroundings and flags obstacles
- **Identifies objects** — objects, currency, everyday products
- **Hands-free** — controlled entirely by voice commands

## Why Snapdragon / On-Device NPU

- **Zero latency** — obstacle warnings can't wait on a cloud round-trip
- **Zero connectivity required** — works in rural areas, transit, anywhere
- **Privacy by design** — camera feed never leaves the device
- **All-day battery life** — Hexagon NPU efficiency vs. CPU/GPU-only pipelines

## Architecture

| Function | Model | Source |
|---|---|---|
| Voice input | Whisper-Tiny | Qualcomm AI Hub (optimized) |
| Object/obstacle detection | YOLOv8-Nano (INT8) | Qualcomm AI Hub |
| Text recognition (OCR) | PaddleOCR / EasyOCR | Converted via AI Hub |
| Scene reasoning | Llama 3.2 1B | Run via QNN SDK |
| Voice output | Piper TTS | Quantized, on-device |

All models are quantized and executed through the **Qualcomm Neural Network
(QNN) SDK**, targeting the Hexagon NPU, with CPU/GPU used only as fallback.

## Status

- ✅ Architecture validated and mapped to Qualcomm AI Hub models
- ✅ Initial OCR → speech pipeline working on-device
- 🔄 Object detection integration (YOLOv8-Nano) — in progress
- 🔄 Full multi-model fusion — next milestone

## Impact

A privacy-first, connectivity-independent assistive tool for an underserved
population of 25M+, while demonstrating genuine multi-model NPU orchestration
on Snapdragon rather than a single-model showcase.

---
**Contact:** Parth Gupta — gparth577@gmail.com
