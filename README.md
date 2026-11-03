\# **Automatic License Plate Recognition (ALPR) System**

**IoT-based license plate recognition system using computer vision, OCR, and ESP32-CAM.**



\## Overview

This project implements an ALPR system designed for vehicle identification and

crime investigation use cases. It combines an ESP32-based hardware design with

a Python simulation pipeline that detects and reads license plates from images

using OpenCV and Tesseract OCR.



\## Hardware Design

Designed in KiCad. Key components:

\- \*\*ESP32-WROOM-32\*\* — main microcontroller

\- \*\*AMS1117-3.3\*\* — 3.3V voltage regulator

\- \*\*ER\_OLEDM0.91 (I2C)\*\* — 0.91" OLED display

\- \*\*FTDI Header\*\* — for serial programming

\- \*\*Resistors:\*\* R1 (10kΩ), R2 (4.7kΩ), R3 (4.7kΩ)

\- \*\*Capacitors:\*\* C1, C2 (10µF)



Schematic and PCB files are included in this repository.



\## Software Simulation

The Python simulation runs the full ALPR pipeline on a local image:



1\. Load image from disk

2\. Preprocess (grayscale → Gaussian blur → adaptive threshold → Canny edges)

3\. Detect license plate contour by aspect ratio and area filtering

4\. Extract plate region

5\. Run Tesseract OCR on the extracted region

6\. Display annotated result



\### Requirements



pip install opencv-python pytesseract numpy



\[Tesseract OCR](https://github.com/tesseract-ocr/tesseract) must be installed separately.



\### Run



python alpr\_esp32\_system.py



Set `IMAGE\_PATH` in the script to your test image filename before running.



\## Repository Contents

| File | Description |

|------|-------------|

| `ALPR\_ESP32\_System.kicad\_sch` | KiCad schematic |

| `ALPR\_ESP32\_System.kicad\_pcb` | PCB layout |

| `ALPR\_ESP32\_System.pdf` | Schematic export (PDF) |

| `ALPR\_ESP32\_System.csv` | Bill of materials |

| `ALPR\_ESP32\_System code note.txt` | Python simulation code and notes |

| `report ALPR\_ESP32.txt` | KiCad ERC report |



\## Status

Hardware design complete. Python simulation pipeline functional.

ESP32-CAM firmware integration in progress.

