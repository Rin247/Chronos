# Chronos — Cross-Platform Matroska (MKV) Inspector & Editor

Chronos is a fast, cross-platform Matroska (`.mkv` / `.mka` / `.webm`) container inspector, stream multiplexer, and header editor. Built around a zero-dependency C++20 EBML parser core, Chronos powers both a Qt 6 / QML desktop workbench (**Vulkan 1.3 and DirectX 12 (Feature Level 12_1) First/Only**) and an Android app (via JNI).

---

## ⚡ Core Subsystems & Status Matrix

| Subsystem | Features & Capabilities | Status / Roadmap |
|---|---|---|
| **Graphics Engine** | **Vulkan 1.3 & DirectX 12 (Feature Level 12_1) First/Only** desktop viewport | Active |
| **EBML Parser** | Zero-dependency C++20 Matroska/WebM parser, seek table inspector, codec ID extraction | Active |
| **Bitstream Analyzer** | Corrupt EBML element repair, keyframe index re-builder, NAL unit inspector | Roadmap |
| **Remuxing Engine** | Zero-re-encode track toggling, audio stream extraction, subtitle insertion | Active |
| **Batch Remuxer** | Multi-file batch remuxing queue, segment linking, font/cover art attachment manager | Roadmap |
| **Tag & Chapter Editor** | Matroska XML/SimpleTag metadata editor, track default/forced flag toggles | Active |
| **Advanced Tagging** | Edition-based chapter editor, ISO language code validator, batch tagger | Roadmap |

---

## 🎬 Key Features & Subsystem Breakdown

### 🔬 EBML & Matroska Inspection (`core/ebml`)
- **Current**: Deep EBML element tree parser, Segment/Cluster seek table inspection, track header parsing (video, audio, subtitles), and codec ID extraction.
- **Planned / Roadmap**: Corrupt element repair, keyframe index builder, and bitstream analyzer.

### ✂️ Track Muxing & Remuxing (`core/mux`)
- **Current**: Track toggling, audio track extraction, subtitle track insertion, and fast remuxing without re-encoding.
- **Planned / Roadmap**: Multi-file batch remuxing, segment linking, attachment manager (fonts / cover art), and WebM optimization.

### 🏷️ Title & Subtitle Header Editor (`core/tags`)
- **Current**: Matroska XML/SimpleTag metadata editor, track name/language tagging, and default/forced track flag toggles.
- **Planned / Roadmap**: Chapter editor (simple and edition-based chapters), automated language code validator, and batch tagger.

---

## 🏗️ Architecture & Technology Stack

- **Graphics APIs**: Vulkan 1.3 & DirectX 12 (Feature Level 12_1) First/Only.
- **Core Engine**: C++20 platform-neutral EBML/MKV library (`core/`).
- **Desktop Shell**: Qt 6.12, QML, CMake.
- **Android Shell**: Kotlin, Jetpack Compose, JNI native bridge.
- **Licensing**: AGPL-3.0.

---

## 🛠️ Building & Running

### Desktop (Windows)
```bat
build.bat Release
run.bat
```

### Android
```bash
./gradlew assembleDebug
```

---

## 📜 License

Chronos is released under the **GNU Affero General Public License v3.0** (AGPL-3.0). See [`LICENSE`](LICENSE) for details.
