# Vehicle Controller 3D 🚗
## Godot 4 — 3D Physics-Based Vehicle Controller

A fully featured **3D vehicle controller** built in Godot 4 (GDScript), supporting multiple vehicles with realistic physics, engine sound simulation, NOS boost, HUD instrumentation, and a rearview camera system.

---

## Vehicles

| Vehicle | Type | Description |
|---|---|---|
| **BMW M3 GTR** | Sports Car | High-performance road car with custom Blender model |
| **4X4 Off-Road** | SUV / Truck | Off-road vehicle with terrain handling |
| **Default Dummy** | Test Vehicle | Barebones template for prototyping |

---

## Features

### 🚗 Vehicle Physics (`VehicleTemplate.gd`)
- Fully custom vehicle physics built on Godot's `VehicleBody3D`
- Per-wheel suspension, steering, and traction control
- Configurable via preset resource files (`.tres`) per vehicle
- Wheel slip detection and ABS/TCS simulation

### 🔊 Engine Sound System (`VehicleSoundController.gd`)
- Multi-layered RPM-based audio blending
- Separate sound layers: idle, low / mid / high RPM, muffler, NOS, gear shift, reverse beep, startup
- Real-time pitch shifting based on engine RPM

### 💨 NOS Boost (`ExtraFeatures.gd` + `NOS.gd`)
- Nitrous Oxide System with depletable tank
- Visual HUD indicator for NOS level

### 📊 HUD & Instrumentation
- **Tachometer** (`Tach.gd`) — animated RPM gauge with redline indicator
- **Speedometer** — real-time speed display
- **Input Logger** (`InputLog.gd`) — visualises throttle / brake / steering inputs
- **Tire Debug View** (`DebugTires.gd`) — per-wheel force and slip display
- **Rearview Camera** (`CarRearview.gd`) — toggleable rear mirror
- **Mini-map** (`MapFrame.gd`) — overhead position tracker

### 🎥 Camera System (`Camera.gd`)
- Smooth follow camera with configurable lag
- Multiple camera modes (chase, cockpit)
- Separate tachometer camera (`TachCamera.gd`)

### ⚙️ Preset System (`VehiclePresetResource.gd` + `PresetMaker.gd`)
- Each vehicle defined as a `.tres` resource file
- Configurable: mass, engine power, gear ratios, suspension stiffness, wheel friction, steering limits, NOS capacity

---

## Project Structure

```
Vehicle Controller 3D/
├── Scripts/
│   ├── Vehicle/
│   │   ├── VehicleTemplate.gd          ← Core physics controller
│   │   ├── VehicleWheel.gd             ← Per-wheel physics
│   │   ├── VehicleInputController.gd   ← Input handling (keyboard/gamepad)
│   │   ├── VehicleSoundController.gd   ← Engine audio system
│   │   ├── VehiclePresetResource.gd    ← Vehicle config resource
│   │   ├── PresetMaker.gd              ← Preset builder tool
│   │   ├── ExtraFeatures.gd            ← NOS, lights, extras
│   │   └── VehicleDebugHelper.gd       ← Debug overlays
│   ├── UI/
│   │   ├── UI.gd                       ← Main HUD controller
│   │   ├── Tach.gd                     ← Tachometer
│   │   ├── NOS.gd                      ← NOS indicator
│   │   ├── CarRearview.gd              ← Rearview mirror
│   │   ├── InputLog.gd                 ← Input visualiser
│   │   ├── DebugTires.gd               ← Tire force display
│   │   ├── MapFrame.gd                 ← Minimap
│   │   ├── Road.gd                     ← Road UI elements
│   │   ├── VehicleVisualController.gd  ← Visual effects
│   │   └── TachCamera.gd              ← Tach camera rig
│   ├── Camera.gd                       ← Follow camera
│   ├── Props.gd                        ← World props (cones, etc.)
│   └── Debug/DebugDraw.gd              ← 3D debug drawing
├── Scenes/
│   ├── Vehicles/
│   │   ├── BMW.tscn                    ← BMW M3 GTR scene
│   │   ├── 4X4.tscn                    ← Off-road vehicle scene
│   │   └── DefaultDummy.tscn           ← Template vehicle
│   └── Road/Cone_1.tscn               ← Traffic cone prop
├── Assets2/
│   ├── Blender/                        ← 3D models (BMW, OffRoad, Props)
│   ├── Font/                           ← Custom fonts
│   ├── Fx/                             ← Visual effects
│   ├── Shader/                         ← Custom shaders
│   ├── Sky/                            ← Skybox
│   └── UI/                             ← HUD textures
├── VehiclePresets/
│   └── BMW GTR M3.tres                ← BMW vehicle preset config
├── Singleton/VehicleControl.gd         ← Global vehicle manager
├── addons/
│   ├── GPUTrail-main/                  ← Tire trail / skidmark effect
│   └── debug_draw_3d/                  ← 3D debug rendering plugin
├── project.godot                       ← Godot project config
└── test.tscn                           ← Main test scene
```

---

## How To Run

1. Install **[Godot 4](https://godotengine.org/download)** (4.x)
2. Open Godot → **Import Project** → select `project.godot`
3. Open `test.tscn` and press **Play**

### Controls (Keyboard)
| Key | Action |
|---|---|
| `W` / `↑` | Throttle |
| `S` / `↓` | Brake / Reverse |
| `A` / `←` | Steer Left |
| `D` / `→` | Steer Right |
| `Space` | Handbrake |
| `Shift` | NOS Boost |

---

## Addons Used

- **[GPUTrail](https://github.com/you-win/godot-gpu-trail)** — GPU-accelerated tire trails / skidmarks
- **[DebugDraw3D](https://github.com/DmitriySalnikov/godot_debug_draw_3d)** — Runtime 3D debug visualisation
