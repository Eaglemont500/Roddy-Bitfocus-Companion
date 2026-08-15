# Bitfocus Companion Control System

A multi-surface Bitfocus Companion configuration designed for unified AV, lighting, and comms control across physical consoles, displays, and remote audio systems.

## 🎛 Control Surfaces

This configuration maps control actions and dynamic feedback across 6 hardware surfaces:

* **2× Elgato Stream Deck +** (Rotary encoders and touch strip pages)
* **2× Elgato Stream Deck XL** (Main layout pages and master controls)
* **2× Elgato Stream Deck MK.2** (Auxiliary and operator surfaces)

## 🔌 Connections & Integrations

| Target Hardware / Software | Integration Method | Capabilities / Scope |
| :--- | :--- | :--- |
| **Soundcraft Si Expression 1** | Mixing Station API / Module | Dynamic channel faders, mutes, and routing |
| **ETC Element 2** | OSC / Native ETC Module | Cue triggers, submasters, and channel levels |
| **6× Displays / Projectors** | Generic HTTP Module | Power ON/OFF, shutter, and input commands |
| **Hollyland Solidcom C1 Pro** | HTTP / Custom API | Mute status & active monitoring for 8 remote headsets |
| **Spotify (External Machine)** | Tech Ministry Module | Remote media playback & track controls |

## ✨ Key Features & Logic

* **Multi-User PIN Lockout:** Utilizes background variable concatenation and conditional triggers to require passcodes before opening restricted control pages.
* **System-Wide Logic & Triggers:** Automated cross-system events and feedback indicators across all surfaces.
* **Layout & ID Mapping:** Clear mapping structure defined in `Stream Deck Descriptions.txt` matching physical button grid positions to target device IDs.

## 📁 Repository Contents

* `configs/` — Contains 3 configuration export formats (`.companionconfig`, etc.) for version flexibility.
* `Stream Deck Descriptions.txt` — Reference sheet outlining physical Stream Deck layouts and device ID assignments.

## 🚀 Installation & Setup

### 1. Install Bitfocus Companion

Choose one of the following deployment methods to install Bitfocus Companion:

**Option A: Homebrew (macOS)**
```bash
brew install --cask companion
```

**Option B: Linux AppImage (Terminal)**
```bash
# Make the downloaded AppImage executable and launch it
chmod +x companion-*.AppImage
./companion-*.AppImage
```

**Option C: Docker Container (Linux / Server)**
```bash
docker run -d \
  --name bitfocus-companion \
  --restart unless-stopped \
  --network host \
  -v companion_data:/companion \
  ghcr.io/bitfocus/companion/companion:latest
```

---

### 2. Import the Configuration

1. **Clone this repository:**
   ```bash
   git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
   cd your-repo-name
   ```
2. Open **Bitfocus Companion** and navigate to the Web Admin UI (default: `http://localhost:8000`).
3. Go to the **Import / Export** tab.
4. Click **Import** and select one of the provided configuration files from the repository.
5. Open `Stream Deck Descriptions.txt` and update target IP addresses under the **Connections** tab to match your local network setup.
