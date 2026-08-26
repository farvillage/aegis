# AEGIS

Standalone, native desktop application for real-time network intrusion detection and behavioral threat analysis in private 5G and IoT environments.

## Overview
AEGIS Desktop provides a native, zero-browser user interface built directly for macOS and Windows. Utilizing CustomTkinter for native window rendering and direct in-memory machine learning execution, it eliminates external server overhead while retaining the core behavioral analytics capabilities of the AEGIS research framework.

## Key Features

    True Native Application Window: Runs independently on the operating system without spawning local web browser tabs or background server ports.

    Direct In-Memory Inference: Ingests raw network traffic captures (.pcap, .pcapng) or structured datasets (.csv) and passes them directly to the embedded Random Forest classification engine.

    Piano-Black Operator Interface: Features custom dark styling (#000000 canvas, #0a0a0a panels, and #484aaa purple accents) tailored for security operations centers (SOC).

## Project Structure
```
AEGIS/
├── backend/
│   ├── model.py (Feature mapping and model inference logic)
│   └── parser.py (Scapy packet parser and flow aggregator)
├── frontend/
│   └── app.py (CustomTkinter native desktop UI controller)
├── aegis_wustl_model.pkl (Pre-trained Random Forest model)
├── aegisicon.png (Source branding asset)
├── aegisicon.icns (Native macOS application dock icon)
├── aegis.spec (PyInstaller multi-module build configuration)
└── pyproject.toml (Project dependency configurations)
```

## Building from Source

To compile AEGIS into a standalone native application binary (.app / executable):

    Install requirements & PyInstaller:
    pip install customtkinter pandas scikit-learn scapy joblib pyinstaller

    Clean and compile using the spec file:
    rm -rf dist build
    pyinstaller aegis.spec --clean

    Locate your binary:
    The finished standalone application bundle will be located inside the dist/ folder.

## Author
Ygor Gesteira

Master's Researcher @ Instituto Federal da Paraíba (IFPB)

Focusing on machine learning applications for cybersecurity in Internet of Medical Things (IoMT) over private 5G networks.
