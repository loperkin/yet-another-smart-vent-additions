# Yet Another Smart Vent — Additions

Modernized **ESPHome configuration, Home Assistant control examples, and additional 3D-printable frame designs** for the excellent **Yet Another Smart Vent** project created by BrobstonCreations.

> **Important:** I did not create the original Yet Another Smart Vent hardware or mechanical vent design. This repository is a companion to that project and contains my own additions along with an updated ESPHome configuration for current versions of ESPHome.

## Original Project

The smart vent hardware and original design were created by **BrobstonCreations**:

https://github.com/BrobstonCreations/yet-another-smart-vent

If you're building one of these vents from scratch, **start there**.

Their repository contains the original:

- Mechanical vent design
- Louvers and vent mechanism
- Electronics and component information
- Assembly instructions
- ESPHome implementation
- 3D-printable parts and original frame sizes

A huge thank you to **BrobstonCreations** and the contributors to that project for designing it and making it available to the community.

This repository exists because I built their project, started using it around my house, and eventually needed some things that weren't available in the original version.

---

# What This Repository Adds

After building the original Yet Another Smart Vent, I ran into two things I wanted to change.

First, the original ESPHome configuration was written for a much older version of ESPHome. ESPHome has changed considerably since then, so getting the vents running on a current installation required a number of updates.

Second, I needed vent frame sizes and configurations that weren't included with the original project.

Rather than changing or replacing the upstream project, I'm keeping those additions here.

This repository contains:

- Updated YAML for current ESPHome versions
- Updated servo configuration and behavior
- Home Assistant focused controls
- Example room-level HVAC automation logic
- Sensor failure fail-safe behavior
- Additional 3D-printable vent frames
- Notes and improvements from using the vents in a real Home Assistant installation

Think of this as a **modern companion to the original project**, not a replacement for it.

---

# Updated ESPHome Configuration

The original Yet Another Smart Vent includes an ESPHome configuration for controlling the vent.

Since that configuration was created, ESPHome has gone through a number of changes. When I built my vents, portions of the original configuration needed to be updated before they would work properly with a current ESPHome installation.

The YAML in this repository is my updated version for the vents I'm currently running.

Changes include updates to:

- Current ESPHome syntax and components
- Servo configuration
- Vent position control
- Movement behavior
- Servo detachment after movement
- Home Assistant integration
- Additional controls used by my HVAC automations

The goal isn't to redesign the original vent controller. It's to keep the same basic hardware concept working cleanly with a modern ESPHome and Home Assistant installation.

My current configuration uses:

- **ESP8266 D1 Mini**
- Servo on **D3**   I use the DFRobot DMS-MG90-A
- **50 Hz** servo frequency
- Approximately **7 second** movement transition
- Automatic servo detachment after movement

My vent calibration currently uses approximately:

- **Open:** 0%
- **Closed:** -80%

Servo limits can vary between builds, so **calibrate your own vent before using these values**.

---

# My 3D Printable Frames

The problem: <img width="140" height="200" alt="ventproblem" src="https://github.com/user-attachments/assets/a2b4010a-c261-4662-9cb8-a01e30924789" />
Original covers did not cover all the wall damage from old vents. 

The frame files contained in this repository are **my own designs**.  <img width="300" height="180" alt="Frameimage" src="https://github.com/user-attachments/assets/c5c81a90-9ff3-47f1-8d7e-3905f943ea98" />


They are not modified copies of the original project's frame STL files.

I designed these additional frames to interface with the mechanical vent assembly from Yet Another Smart Vent because I needed sizes or configurations that weren't available for some of the registers in my house.

The relationship is essentially:

**BrobstonCreations vent mechanism + my frame = additional vent size**

The frames still depend on the original project's mechanical components, so you'll need the original vent parts to use them.

For the louvers, gears, servo mechanism, electronics mounting, assembly instructions, and other original components, visit:

https://github.com/BrobstonCreations/yet-another-smart-vent

## Available Frame Sizes see 3d Print folder for STL files. 

<!-- Add your actual frame sizes here -->

- 4X10
- 6x12
- TBD

Additional sizes may be added as I install more vents.

---

# Licensing & Attribution

The original **Yet Another Smart Vent** project is the work of BrobstonCreations and is distributed under its own license.

Original project:

https://github.com/BrobstonCreations/yet-another-smart-vent

This repository does not claim ownership of the original vent mechanism, hardware design, documentation, or other upstream work.

The additional 3D-printable frames included here are my own original designs created to interface with that system.

The updated ESPHome configuration is provided to help users run this hardware with current versions of ESPHome and Home Assistant.

Please refer to the original repository for its licensing terms and attribution requirements when using or modifying material originating from that project.

And if this repository helps you build one, please give the **original Yet Another Smart Vent project a star as well**. They did the hard part that made these additions possible.

---

**Learn it. Build it. Put it into practice.**
