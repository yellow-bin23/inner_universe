# Inner Universe · Prototype Scope

> Version: Prototype v0.1  
> Goal: Validate the core experience of “entering a living inner universe” before building a complete product.

## 1. Prototype Objective

This prototype does not aim to implement the complete Inner Universe system.

It should validate one central experience:

> The user can observe a living psychological universe, move through it continuously, approach one psychological object, and sense that it slowly reveals itself through attention.

The prototype must feel like one continuous consciousness space rather than a set of application pages.

## 2. In Scope

The first version includes only the following capabilities.

### 2.1 2.5D Macro Universe Home

Create a mobile-first 2.5D inner-universe home scene.

The scene should include:

- Deep blue-black consciousness space with intentional empty darkness
- A small, stable warm-golden Self seed near the center
- Layered depth: foreground, middle distance, and deep background
- Slow drifting dust, faint purple shadow mist, and subtle distant lights
- No dashboard-style panels or heavy side navigation
- UI remains minimal and visually subordinate to the universe

The visual priority is not realism. It is a calm, living, psychologically symbolic space.

### 2.2 Continuous Camera Zoom

Use one scene and one camera controller.

The prototype must support:

- Dragging/panning across the macro universe
- Pinch or wheel zoom
- Smooth camera focus toward a selected object
- Smooth return to the macro view
- No route changes or conventional page transitions

The user should feel that they are moving deeper into the same world.

### 2.3 Self Breathing

The Self is a small warm-golden seed, not a sun.

It should have:

- Very subtle scale breathing
- Soft internal glow
- Low-frequency pulsing
- Gentle circular disturbance or dust response around it

The Self should feel stable, quiet, ancient, and always present.

### 2.4 Five Psychological Objects

Implement exactly five visual psychological objects. They should be distinct in morphology and behavior, not generic circular nodes.

Suggested first set:

1. **Trauma** — cracked amber-like memory crystal with frozen internal particles  
2. **Creativity** — branching translucent growth with cool-blue bioluminescent tips  
3. **Intimacy** — two interwoven translucent structures that gently approach and separate  
4. **Avoidance** — fragmented floating shards that drift away from attention  
5. **Shadow** — irregular low-contrast form partly hidden in slow purple mist  

Each object needs:

- Position in the macro space
- Distinct silhouette
- Slow idle life movement
- Soft semantic color variation
- Click/tap focus behavior

Do not add labels by default. Labels may appear only after an object has been focused.

### 2.5 Early Gaze / Revelation Prototype

Implement a minimal version of “attention reveals the object.”

When a user focuses on an object and remains still:

- At 0–5 seconds: only the base contour and dim internal light are visible
- At 5–15 seconds: a new texture, crack, fiber, or inner particle layer fades in
- At 15+ seconds: a small visual clue appears, such as a memory filament, hidden fragment, or a short unnamed prompt

This is not a content system yet. It is a visual proof of the revelation mechanic.

Use a simple local timer and `revealLevel` state. No AI analysis, persistent user profile, or real psychological inference in v0.1.

### 2.6 No Page Navigation

The prototype must not include:

- Conventional multi-page navigation
- Tab bars
- Sidebars
- Detail pages
- Chat history panels
- Dashboard cards
- Reports, scores, or progress charts

A minimal back affordance may appear only when the camera is focused on an object.

## 3. Technology Direction

### Required Stack

- React
- TypeScript
- React Three Fiber
- Three.js
- Drei
- Zustand or equivalent lightweight state store

### First-Version Rendering Strategy

Do **not** build complex custom shaders at the beginning.

Use:

- Drei helpers
- Basic materials
- Transparent texture planes
- Points / particle systems
- Simple sprites
- Built-in or lightly modified `MeshPhysicalMaterial`, `MeshStandardMaterial`, and transparent materials
- Noise-driven position offsets in JavaScript
- Mild bloom, fog, depth, and blur only when performance permits

The first goal is to validate camera movement, object identity, depth, stillness, and revelation.

### Shader Upgrade Policy

The four major materials may later receive custom shader treatment:

- Conscious Glass
- Crystal Memory
- Living Fiber
- Shadow Mist

Do not implement those shaders until the Gaze experience is visibly compelling with simpler materials.

## 4. Interaction Rules

### Macro State

- User drags to explore
- User zooms to change psychological distance
- User taps an object to focus it
- Self remains visible or inferable as a stable center

### Focus / Gaze State

- Camera moves close to the selected object
- Most UI fades away
- Object becomes visually dominant
- A tiny prompt may indicate: “停留，更多会显现”
- Staying still increases `revealLevel`
- Zooming out or tapping back returns to macro view

## 5. Visual Constraints

Maintain the project visual language:

- Deep blue-black background: `#060B14`
- Warm Inner Gold for Self
- Restrained Shadow Violet
- Very subtle Insight Cyan
- Large areas of darkness and quiet negative space
- Low information density
- Slow meditative motion

Avoid:

- NASA-style galaxy imagery
- Planets, spaceships, and sci-fi HUDs
- Cyberpunk colors
- Uniform bubble nodes
- Explicit graph lines
- Heavy glass cards
- Chat bubbles
- Game-like quest UI
- Bright RGB lighting
- Fast or flashy animation

## 6. Explicitly Out of Scope

The following are not part of Prototype v0.1:

- AI mirror dialogue
- Real user accounts
- Backend database
- User-generated psychological records
- Automated psychological classification
- Persistent discovery history
- Full Region View
- Full Dialogue / Consciousness View
- Advanced shader system
- Full mobile production optimization
- Accessibility and localization completeness
- Analytics or monetization

## 7. Acceptance Criteria

The prototype is successful when a tester can:

1. Open one immersive 2.5D universe scene  
2. Drag and zoom without entering a new page  
3. Notice the Self as a small stable breathing center  
4. Recognize five objects as visually different psychological presences  
5. Tap one object and smoothly enter a focused gaze state  
6. Remain still and witness at least one new layer of that object reveal itself  
7. Return to the macro universe smoothly  
8. Describe the experience as “exploring an inner space,” not “using a dashboard”  

## 8. Suggested Build Order

1. Project scaffold: React + TypeScript + R3F + Drei  
2. Macro scene, camera controller, drag and zoom  
3. Self seed and low-frequency breathing  
4. Five object components with basic materials and idle motion  
5. Focus camera transition and UI fade  
6. Local `revealLevel` timer and staged visual layers  
7. Performance pass for mobile viewport  
8. Only then decide whether custom shaders are justified  

## 9. Deliverable

A single playable mobile-first web prototype.

Minimum demo flow:

> Enter macro universe → drag / zoom → choose one object → camera focuses → remain still → a hidden visual layer appears → return to macro universe.

The v0.1 prototype is not required to explain the user psychologically.

It only needs to make one proposition emotionally believable:

> Attention can make a hidden part of the inner world become more visible.
