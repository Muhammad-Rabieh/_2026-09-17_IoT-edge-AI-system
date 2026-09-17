# IoT & Edge AI System — Architecture Overview Demo

An interactive diagram showing how the proposed IoT + Edge AI system fits
together end to end — from sensors and cameras on-site, through local
processing, to the backend and dashboard.

<img width="1346" height="582" alt="Peek 2026-09-17 13-20" src="https://github.com/user-attachments/assets/e5f59d21-81df-4d66-a0d1-1a87c3946c66" />


**File:** `iot-edge-ai-system-diagram.html` — open directly in any browser.

## What it shows

The diagram lays out the system as connected modules, with animated pulses
traveling along the connections to represent live telemetry and, periodically,
an AI-triggered alert event — so you can see how data would move through the
system in operation, not just a static diagram.

**Modules:**

| Module | Role in the system |
|---|---|
| Sensor Node | On-site sensor unit collecting the required measurements |
| Camera Feeds | Video sources feeding the vision pipeline |
| Radio Link | Wireless connection carrying sensor data to the local gateway |
| Edge AI Inference | Computer vision model that watches camera feeds and detects events locally, without needing the cloud |
| Edge Gateway | Local processing unit that collects everything happening on-site |
| Backend Server | Central server that stores data and distributes alerts |
| Web Dashboard | Real-time view of live data, device status, and alerts |
| Power & Battery | Power delivery to the on-site hardware |

**How data and power flow:**

- **Power**: the Power & Battery module supplies exactly three things — the
  Sensor Node, the Cameras, and the Edge Gateway.
- **Sensor path**: Sensor Node → Radio Link → Edge Gateway.
- **Vision path**: Cameras → Edge AI Inference → Edge Gateway.
- **Everything meets at one point**: all data, from both sensors and
  cameras, comes together at the Edge Gateway before going anywhere else —
  nothing skips it.
- **To the cloud/office**: Edge Gateway → Backend Server → Web Dashboard.

## How to use it

- **Hover** a module to highlight it and see exactly what it connects to.
- **Click** a module to open a short description of what it does and what
  it's built from. Click again, or click empty space, to close it.
- Watch the top-left status line: it normally reads "system nominal," and
  periodically switches to an alert message to demonstrate how a detected
  event would travel from the cameras all the way to the dashboard in real
  time.

## Purpose of this demo

This is a visual walkthrough of the system's architecture, meant to make the
proposal concrete and easy to discuss — it is not a working prototype and
isn't connected to real hardware, sensors, or a live server. It exists so we
can talk through the design, agree on the data flow, and confirm this
matches your requirements before development starts.
