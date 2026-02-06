# 🧩 Unreal Engine Blueprint Showcase — Volume 8

A curated collection of **Unreal Engine 5.5.4** mini-projects — each one a focused, standalone system demonstrating clean, production-ready Blueprint design.
This sandbox contains **Projects 1–6**, wrapped together as a complete learning pack.
Each system is lightweight, modular, and built to scale into full gameplay features.

---

## 🎞️ Project Gallery

![Project Showcase](Media/all.gif)

Explore the projects below 👇
Each entry includes a **Blueprint workflow**, **GIF preview**, and **feature breakdown** — perfect for learning, prototyping, or integrating directly into your own UE projects.

---

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

--- 

# Project 3 – Vehicle Weapons and Destruction

## 🖼️ Preview

![Vehicle Weapons and Destruction](Media/3.gif)

## 🧱 Features

**Vehicle-Mounted Weapon System**

- Weapon mesh mounted directly to an existing Chaos Vehicle
- Dedicated **Muzzle** scene component used as a projectile spawn point
- Fire input handled through Enhanced Input with a digital action

**Projectile Blueprint**

- Custom **BP_Bullet** actor with separate collision and visual mesh
- Projectile Movement component with high-speed forward velocity
- Bounce enabled for ricochet-style impacts
- Emissive bullet material for clear visual feedback

**Physics Impact Logic**

- On-hit logic gated with Do Once to prevent repeated force application
- Physics impulse applied based on projectile velocity
- Impulse applied at hit location for more natural reactions

**Chaos Destruction Integration**

- Chaos **FS_MasterField** spawned at impact point
- High strain magnitude applied to guarantee visible fracture
- Field triggered immediately to break Geometry Collections on contact

**Impact Feedback**

- Explosion particle effect spawned at hit location
- Impact sound played on collision
- Muzzle flash and firing sound triggered when weapon fires

**Destructible Targets**

- Geometry Collections created from simple meshes
- Reduced damage thresholds for easier breakage
- Removal on Sleep enabled to clean up fractured debris

## 🚀 Result

A fully functional vehicle-mounted weapon system that fires high-speed projectiles capable of applying physics force and destroying Chaos Geometry Collections in real time while driving. 

--- 

# Project 4 – Chaos Vehicle Visual Wheel Stance System

## 🖼️ Preview

![Chaos Vehicle Wheel Stance](Media/4.gif)

## 🧱 Features

**Cosmetic Wheel Camber Control**

- Wheel camber applied using **Transform (Modify) Bone** nodes in the wheel Animation Blueprint  
- Rotation applied in **Parent Bone Space** to maintain clean skeletal behavior  
- Fully visual implementation with **no impact on Chaos Vehicle physics or handling**

**Lateral Wheel Shift (Track Width Adjustment)**

- Shared float variable controls lateral wheel offset  
- Translation applied per wheel bone for visual stance width  
- Vector negation used to mirror offsets correctly between left and right sides

**Per-Side Mirroring Logic**

- Single camber and shift values reused across all wheels  
- Rotator inversion used to flip camber direction per side  
- Clean setup avoids redundant variables and keeps the system extensible

**Ordered Bone Modification Chain**

- Wheel bones modified in a controlled, sequential chain  
- Front and rear wheels processed independently  
- Reroute nodes used to maintain readability and clean data flow in the Anim Graph

## 🚀 Result

A clean, extensible visual stance system that allows Chaos Vehicles to be cosmetically customized using wheel bone animation. This setup provides precise control over camber and track width while keeping vehicle physics untouched, making it ideal for stylized builds, customization systems, or future extensions like drift and ride height tuning.

--- 

# Project 5 – Interface Wizard: Capability-Based Interaction System

## 🖼️ Preview

![Interface Wizard](Media/5.gif)

## 🧱 Features

**Blueprint Interface Design**

- Uses **BPI_Scalable** to define a capability rather than an actor type  
- Interface exposes a single Grow/Shrink function with a float input  
- World actors interact without casting or class checks  

**Player Interface Implementation**

- Player character implements BPI_Scalable  
- Scale changes routed through a dedicated size change function  
- Current scale tracked internally and updated incrementally  
- Scale values clamped to prevent extreme sizes  

**Wizard Interaction Actors**

- Increase Wizard applies positive scale change on overlap  
- Decrease Wizard applies negative scale change on overlap  
- Collision-based interaction using sphere trigger  
- Interface presence checked before sending requests  
- Non-compatible actors safely ignored with debug feedback  

**Wandering AI Integration**

- Wandering AI optionally implements the same interface  
- AI responds to wizards using identical logic as the player  
- No changes required to wizard behavior  
- Demonstrates shared interaction across player and AI  

**Capability-Based Gameplay Pattern**

- World logic operates on supported behavior, not actor identity  
- Actors fully control how they respond to interface requests  
- Scales cleanly to players, AI, or future interactable actors  

## 🚀 Result

A reusable interaction system driven entirely by Blueprint Interfaces.  
World actors apply effects without knowing who they interact with, and only actors that opt into the capability respond. This pattern cleanly separates interaction intent from implementation and works consistently across players and AI.

--- 

# Project 6 – First Person Blend Space Locomotion

## 🖼️ Preview

![Project 6](Media/6.gif)

## 🧱 Features

**First Person Character Blueprint**

- Custom `BP_FPCharacter` built from a blank template
- Camera component with controller pitch rotation enabled
- Isolated first person arms mesh attached to the camera
- Clean movement defaults with scalable speed values

**Enhanced Input System**

- Dedicated `IMC_Default` input mapping context
- Axis-based movement actions for forward/backward and strafing
- 2D camera look input using mouse XY with corrected vertical inversion
- Boolean sprint action driving temporary speed changes

**Movement and Sprint Logic**

- Camera-relative movement using control rotation vectors
- Smooth walk and sprint transitions by modifying max walk speed
- No hard-coded state checks or animation toggles

**Animation Blueprint Setup**

- Arms-only Animation Blueprint bound to a custom skeleton
- Cached reference to the character for safe data access
- Real-time speed calculation using horizontal velocity length

**Speed Driven Blend Space**

- 1D Blend Space driven purely by character movement speed
- Idle, walk, and sprint animations aligned to actual speed values
- Smoothing with ease in/out blending for natural transitions
- No animation state machine required

## 🚀 Result

A clean and scalable first person locomotion system driven entirely by real movement speed.  
The setup avoids rigid animation states, making it easy to extend with additional movement types, weapon animations, or camera effects without refactoring the core logic.
