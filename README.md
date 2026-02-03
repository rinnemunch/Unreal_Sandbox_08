# Project 1 – Blueprint Functions Temperature System

## 🖼️ Preview

![Temperature System](Media/1.gif)

## 🧱 Features

**Temperature Light Blueprint**

- Directional Light converted into a reusable **BP_TemperatureLight**
- Light temperature driven using Kelvin values
- Default neutral value set to **6500** for balanced daylight

**Centralized Temperature Function Logic**

- Single Blueprint function handles all temperature changes
- Float input controls how much the temperature increases or decreases
- Internal clamp ensures values stay between **1700** and **12000**
- Updated temperature returned for external use

**Input-Driven Gameplay Control**

- Left Mouse Button increases Kelvin for cooler lighting
- Right Mouse Button decreases Kelvin for warmer lighting
- No Tick or per-frame logic used
- All changes triggered explicitly through input

**UI Feedback Without Bindings**

- **WBP_TemperatureDisplay** created once on BeginPlay
- Temperature value updated via a dedicated widget function
- Rounded float values displayed for readability
- UI updated only when temperature changes

**Clean Graph Organization**

- Initialization logic grouped and color-coded
- Input actions clearly separated and labeled
- Visual structure reinforces data flow and intent

## 🚀 Result

A clean, input-driven Blueprint system that demonstrates how functions manage state, accept inputs, return values, and drive both gameplay logic and UI feedback. This project focuses on clarity, predictability, and real-world Blueprint function usage without unnecessary complexity.

--- 

# Project 2 – Mixamo First Person Arms Pipeline

## 🖼️ Preview

![Mixamo FP Arms](Media/2.gif)

## 🧱 Features

**Project Setup**

- Unreal Engine 5.5.4 project created using the First Person Template
- Project scoped strictly for animation and mesh validation
- No gameplay logic or systems added beyond default template behavior

**Mixamo Character Selection**

- Character selected based on arm proportions suitable for first person view
- Single test animation chosen to validate the pipeline
- Character downloaded using default Mixamo FBX settings with skin and animation

**Blender Arm Extraction**

- Mixamo FBX imported into Blender 5.0.1
- Full body mesh edited to isolate arm geometry only
- Skeleton preserved to maintain animation compatibility
- Unwanted body geometry removed in Edit Mode for clean arm mesh

**Unreal Engine Import and Validation**

- Edited arm mesh exported from Blender as FBX
- Arms imported into Unreal Engine for testing
- Animation sequence previewed directly to validate mesh and skeleton
- Default First Person arms replaced with custom Blender-extracted arms
- Animation assigned directly without Animation Blueprint for simplicity
- Transform adjusted to align arms correctly in first person view

## 🚀 Result

A clean and flexible foundation for custom first person animations, free from reliance on the default template arms. This setup confirms that Mixamo animations and Blender-edited meshes can be reliably used in a first person context, enabling future expansion into sprinting, blend spaces, and more advanced animation systems.
