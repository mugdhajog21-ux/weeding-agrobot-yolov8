# weeding-agrobot-yolov8
YOLOv8n-based autonomous agricultural robot for inter- and intra-row weeding using computer vision, Raspberry Pi, and pneumatic actuation.
# Weeding Agrobot – YOLOv8n-Based Crop and Weed Detection

An autonomous agricultural robot prototype for inter-row and intra-row
weeding using computer vision, YOLOv8n object detection, Raspberry Pi,
and electromechanical actuation.

## Overview

This project presents the development of an autonomous weeding agrobot
designed to perform both inter-row and intra-row weeding in spring onion
cultivation.

A camera captures images of the crop and surrounding weeds. A lightweight
YOLOv8n object detection model identifies onion plants and weeds. The
model is deployed on a Raspberry Pi, which coordinates motor control and
the pneumatic actuation mechanism used for intra-row weeding.

The system was developed and experimentally evaluated as part of the
research work published in Agricultural Science Digest.

## Research Paper

**Development of a Weeding Agrobot Prototype for Inter-row and
Intra-row Weeding**

Mugdha S. Jog and Sudhir D. Agashe

Agricultural Science Digest, 45(6), 1040–1049, 2025/2026.

DOI: 10.18805/ag.D-6307

Paper:
https://arccjournals.com/journal/agricultural-science-digest/D-6307

## Key Results

- YOLOv8n object detection model
- mAP@50: 0.85
- YOLOv8n model size: 5.96 MB
- Reported inference time: 2 ms
- Overall weeding efficiency: 86%
- Plant/crop damage: 4%
- Field capacity: 0.023 ha/hour
- Prototype performance index: 1726.26
- Real-time deployment on Raspberry Pi 4B+
- Operating speed reported at approximately 0.12 m/s
- Designed for both inter-row and intra-row weeding

## System Architecture

```text
                    ┌───────────────────┐
                    │   Camera / Image  │
                    │     Acquisition   │
                    └─────────┬─────────┘
                              │
                              ▼
                    ┌───────────────────┐
                    │   YOLOv8n Object  │
                    │     Detection     │
                    └─────────┬─────────┘
                              │
                     Crop / Weed Detection
                              │
                              ▼
                    ┌───────────────────┐
                    │   Raspberry Pi    │
                    │  Decision &       │
                    │  Control Logic    │
                    └───────┬─────┬─────┘
                            │     │
                 ┌──────────┘     └──────────┐
                 ▼                           ▼
        ┌─────────────────┐        ┌─────────────────┐
        │ Motor / PWM     │        │ Pneumatic       │
        │ Control         │        │ Actuation       │
        └─────────────────┘        └────────┬────────┘
                                            │
                                            ▼
                                   Intra-row Weeding
