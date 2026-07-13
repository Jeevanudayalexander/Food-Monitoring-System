# Smart FIFO Stock Control System for Comestible Storage Units

A Raspberry Pi-based smart interface that automates First-In-First-Out (FIFO) stock control in food storage units — built to replace manual, sticker-based inventory tracking in hotel kitchens with real-time, QR-driven monitoring.

> Developed as part of a project internship at Hotel Mangala International, Coimbatore, and presented as a final-year review project at PSG College of Technology.

## Problem Statement

In hotel kitchens and F&B storage, stock is typically tracked using handwritten labels and manual FIFO checks. As inventory volume grows, this becomes error-prone — expired items go undetected, FIFO order breaks down, and food wastage rises. This project builds an automated, sensor-driven alternative that removes manual guesswork from stock rotation.

## Objectives

- Automate FIFO-based stock arrangement and retrieval
- Track comestible items by time to flag near-expiry or expired stock
- Use QR-based identification for every stored item
- Provide visual and audible alerts for expired or critical stock
- Reduce manual effort and food wastage through a simple, user-friendly interface

## System Overview

**Hardware**
- Raspberry Pi 3 B+ (core processing and control)
- Camera module / USB webcam (QR scanning)
- 58 mm thermal printer (QR code generation)
- Inductive proximity sensor (item detection)
- 3.5" touch display + external HDMI monitor (UI)
- Buzzer module (expiry/violation alerts)
- 12V SMPS power supply with converters

**Software**
- Python, OpenCV, Pyzbar (QR generation/decoding)
- Tkinter (GUI)
- Raspberry Pi OS (Bookworm)
- Local database/file system for inventory records

**Key Features**
- Intelligent FIFO enforcement with violation alerts
- QR-based item traceability
- Real-time monitoring with visual + buzzer alerts
- Compact, integrated hardware design (custom 3D-printed enclosure)

## How It Works

1. **Stock entry** — user enters item details via the touchscreen GUI; the system generates and prints a unique QR code, which is attached to the item before storage.
2. **Detection** — a proximity sensor detects item placement/removal in the storage unit, and the item's timestamp is logged in the database.
3. **Retrieval** — scanning an item's QR code checks its timestamp against other stored items. Oldest-first retrieval is allowed; retrieving an item out of order triggers a FIFO violation alert.
4. **Expiry tracking** — the system continuously checks expiry dates, flags near-expiry stock, and blocks expired items from use, with alerts shown on-screen and via buzzer.

## Results

- FIFO-based stock monitoring implemented and validated end-to-end on Raspberry Pi
- QR generation and scanning worked reliably for item identification
- Real-time inventory updates and correct FIFO validation confirmed during testing
- Expiry detection and alerting functioned as intended, with stable system operation throughout testing

## Challenges

- Driver compatibility issues on Raspberry Pi OS Bookworm
- Thermal printer latency during QR printing, and its need for a constant current supply
- Limited proximity sensor range (~8 mm)
- Touch display response latency
- Integrating multiple hardware modules into one coordinated pipeline

## Future Scope

- Cloud-based remote monitoring
- Companion mobile app for stock management
- AI-based demand prediction for smarter inventory planning

## Team

- Jeevan Uday Alexander U
- Muhammed Roshan S
- R Mrithun Chokkalingam
- Ragul S J

Department of Robotics and Automation Engineering, PSG College of Technology, Coimbatore
Industrial Mentor: Mr. Sojesh Somapalan
