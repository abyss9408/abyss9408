# Hi, I'm Bryan 👋

I'm a final year computer science undergraduate with a passion for building things from the ground up — game engines, graphics pipelines, embedded systems, and everything in between. I love working close to the metal and understanding how systems actually work.

---

## 🧠 Interests

Beyond systems programming and graphics, I'm interested in **AI and machine learning** — particularly supervised and unsupervised learning algorithms. I enjoy exploring how models learn patterns from data, from classical techniques like regression and clustering to more complex approaches, and applying them to real-world problems.

---

## 🛠️ Tech Stack

**Languages**

![C](https://img.shields.io/badge/C-A8B9CC?style=flat&logo=c&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=flat&logo=csharp&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat&logo=kotlin&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=mysql&logoColor=white)

**Tools & Frameworks**

![Visual Studio](https://img.shields.io/badge/Visual%20Studio-5C2D91?style=flat&logo=visualstudio&logoColor=white)
![VS Code](https://img.shields.io/badge/VS%20Code-007ACC?style=flat&logo=visualstudiocode&logoColor=white)
![WSL](https://img.shields.io/badge/WSL-0078D4?style=flat&logo=windows&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)

---

## 🚀 Featured Projects

### 🎮 Bass N' Kick — 2D Game with Custom Engine (GAM200)
Duration: Sep 2024 - Apr 2025
> A 2D platformer built on a fully custom C++ game engine, developed as a second-year software engineering project.

**My Contributions**

<details>
<summary><strong>Entity Hierarchy & Prefab System</strong> (Largest sustained effort)</summary>

- Implemented the full parent-child hierarchy system, including local transforms, rotation handling, and cascaded deletion
- Built the entire Prefab pipeline end-to-end: Prefab Manager, serialization/deserialization, editing, loading, saving, and instance synchronization
- Added nested prefab support with correct serialization, deserialization, and instantiation
- Auto-tagging of prefab instances; fixed `UIComponent` sync across all prefab instances
</details>

<details>
<summary><strong>Editor & UI (ImGui)</strong></summary>

- Implemented game view docking and rendering inside an ImGui window
- Built the Asset Browser with drag-and-drop for textures/audio, Font Awesome icons, directory navigation, and texture search
- Entity tags editing/display, selected-entity border highlight, and component removal
- Entity drag-and-drop for reordering and creating hierarchies (including promoting entities back to root)
- Layer matrix editor (collision layer interaction grid)
- Refactored Inspector to use ImDraw lists; improved vec2 editing via dragging
</details>

<details>
<summary><strong>Camera System</strong></summary>

- Implemented the in-game camera gizmo (ImGui controller + view frustum visualization)
- Built the Game Camera system, dynamic camera icon sizing, and per-scene camera settings serialization
- Moved editor camera controls from ImGui window to keyboard/mouse input; inverted camera drag
</details>

<details>
<summary><strong>Serialization & Scene Management</strong></summary>

- Added file-based save/load to the serializer; refactored scene/prefab dialogs to use native Windows file dialogs
- Implemented multi-scene loading/saving with per-scene camera settings
</details>

<details>
<summary><strong>Core Engine Infrastructure</strong></summary>

- Entity cloning system (including Clone System updates for nested prefabs)
- Crash handler implementation
- Logger enhancements: multi-destination support and architectural refactor
- Event System upgrade to support standalone function subscriptions
- Input System refactoring; fixed `KeyTriggered` and `MouseButtonTriggered` edge cases
- Fixed Timer to correctly sync actual frame time with fixed delta time
</details>

<details>
<summary><strong>Build & Installer</strong></summary>

- Set up the release build configuration (fullscreen default, ImGui stripped, console disabled)
- Built and maintained the full installer pipeline using InnoSetup: desktop shortcut, game icon, SFX channel fixes, animation fixes
</details>

---

### 🎮 Tangled Memories — 3D Game with Custom Engine (GAM300)
Duration: Sep 2025 - present
> A 3D game built on a custom C++ engine, with a focus on a production-quality graphics pipeline.

**My Contributions**

<details>
<summary><strong>Graphics Library (Core & Foundation)</strong></summary>

- Set up the initial rendering pipeline, core implementation, and include structure
- Implemented SSBO-based GPU instancing and bindless textures
- Built PBR lighting with separated lighting functions and Cook-Torrance BRDF
- Refactored the pipeline into a single unified render pipeline with toggleable passes
- Added gamma correction for albedo/diffuse textures and debug drawing for AABBs and light positions
- Wrote the standalone graphics test driver
</details>

<details>
<summary><strong>Shadow System</strong></summary>

- Implemented point light shadows and spot light shadow visibility
- Added per-light `castShadows` flag; refactored `LightComponent` for per-light shadow control
- Hash-based transform change detection and scene bounds caching to optimize shadow map updates
</details>

<details>
<summary><strong>Material Pipeline</strong> (Significant ownership area)</summary>

- Designed the 3-tier material system (`Material` / `MaterialInstance` / `MaterialPropertyBlock`) following Unity conventions
- Implemented `MaterialPropertyBlock` for lightweight per-object property overrides that preserve GPU instancing
- Built material property serialization/deserialization and integrated the pipeline with the resource system and editor inspector
- Fixed multi-material support, mesh/material change reactivity, and texture coordinate flipping
</details>

<details>
<summary><strong>Text & Font Rendering</strong></summary>

- Built the text rendering system from scratch including the font system (glyph loading and spacing)
- Added World Text rendering with full and cylindrical billboarding
- Fixed crash on text longer than 4 characters and glyph spacing issues
- Wrote Screen Text and World Text usage guides
</details>

<details>
<summary><strong>Scene Graph, Skybox & Physics Debug Rendering</strong></summary>

- Implemented the hierarchical scene graph on the engine side
- Full skybox pipeline: engine/editor integration, texture slot assignment, and scene save/load support
- Integrated JoltPhysics `DebugRenderer` into the editor game view; fixed clearing issues and ghost collider artifacts
</details>

<details>
<summary><strong>Editor & UI</strong></summary>

- Implemented entity picking in the scene viewport
- Set up and tuned ImGuizmo with Unity-style keybindings (Q/W/E/R); fixed crash on entity deletion
- Inspector improvements: drag speeds for vec2/vec3, color picker for lights, material property overrides display
</details>

<details>
<summary><strong>Stability & Build Health</strong></summary>

- Resolved multiple crash sources: message queue race conditions, open-project crash in release mode, ImGuizmo deletion crash, shared mesh mutation bug
- Fixed linker errors, build errors, and compiler errors across multiple integration points
- Cleaned up static analysis warnings; configured external library headers as SYSTEM includes
- Added memory leak checks for the editor; centralized all `.md` documentation into `/docs`
- Implemented delta time calculation and fixed its accuracy
</details>

---

### 📱 TinyCell — Android Marketplace App (CSD3156)
Duration: Jan 2026 - Feb 2026
> A native Android peer-to-peer marketplace app (Carousell-style) built with Kotlin and Jetpack Compose, developed as a third-year mobile computing module project. Follows MVVM clean architecture with an offline-first dual-write strategy across Room (local) and Firebase Firestore (remote). AI tools were leveraged during development to accelerate implementation and assist with architecture decisions.

**Team of 5 | Role: Android Developer**

**My Contributions**

<details>
<summary><strong>Real-time Buyer-Seller Chat System</strong> (Largest contribution)</summary>

- Designed and built the full chat system from scratch — `ChatRepository`, `ChatRepositoryImpl`, `FirestoreChatDataSource`, `ChatMessageDao`, domain models (`ChatMessage`, `ChatRoom`), DTOs, and Firestore data sources
- Implemented real-time message sync via Firestore snapshot listeners with local Room caching for offline support
- Built `ChatScreen.kt` and `ChatViewModel.kt` with live `StateFlow`-driven UI updates
- Updated the navigation graph with parameterised chat routes; integrated chat entry point from the listing detail screen
</details>

<details>
<summary><strong>Seller Listing Dashboard</strong></summary>

- Built `MyListingsScreen.kt` and `MyListingsViewModel.kt` for sellers to view and manage their posted listings
- Created `ListingChatsScreen.kt` and `ListingChatsViewModel.kt` to aggregate all buyer conversations per listing into a single seller-facing view
- Added corresponding Firestore data source methods and updated Firestore security rules
</details>

<details>
<summary><strong>Offer / Price Negotiation Feature</strong></summary>

- Implemented the full offer system end-to-end: `OfferRepository`, `OfferRepositoryImpl`, `FirestoreOfferRepositoryImpl`, `OfferDao`, `OfferEntity`, and `OfferDto`
- Integrated offer flow into the existing chat UI (`ChatScreen`, `ChatViewModel`)
- Refactored `FirestoreListingRepositoryImpl` and `ListingRepository` to accommodate offer-related operations
</details>

<details>
<summary><strong>Listing Detail & Marketplace UI</strong></summary>

- Overhauled `ListingDetailScreen.kt` with a reworked layout and improved information hierarchy
- Extracted reusable marketplace UI components into `MarketplaceComponents.kt` (listing cards, price tags, user avatars, message bubbles)
- Refactored `HomeScreen.kt` and extended `ListingRepository` with additional query support
</details>

---

## 📌 Featured Repositories

<p align="left">
  <a href="https://github.com/abyss9408/gam100">
    <img src="https://github-readme-stats-fast.vercel.app/api/pin/?username=abyss9408&repo=gam100&theme=tokyonight&hide_border=true" alt="First Year Undergraduate Project 1" />
  </a>
  <a href="https://github.com/abyss9408/gam150">
    <img src="https://github-readme-stats-fast.vercel.app/api/pin/?username=abyss9408&repo=gam150&theme=tokyonight&hide_border=true" alt="First Year Undergraduate Project 2" />
  </a>
  <a href="https://github.com/abyss9408/gam200">
    <img src="https://github-readme-stats-fast.vercel.app/api/pin/?username=abyss9408&repo=gam200&theme=tokyonight&hide_border=true" alt="Second Year Undergraduate Project (Bass N' Kick)" />
  </a>
  <a href="https://github.com/gsherman01/CSD3156-Android-App">
    <img src="https://github-readme-stats-fast.vercel.app/api/pin/?username=gsherman01&repo=CSD3156-Android-App&theme=tokyonight&hide_border=true" alt="Mobile Computing Project (TinySell)" />
  </a>
  <a href="https://github.com/abyss9408/UndergraduateCoursework">
    <img src="https://github-readme-stats-fast.vercel.app/api/pin/?username=abyss9408&repo=UndergraduateCoursework&theme=tokyonight&hide_border=true" alt="Undergraduate Coursework" />
  </a>
  <a href="https://github.com/abyss9408/DiplomaCoursework">
    <img src="https://github-readme-stats-fast.vercel.app/api/pin/?username=abyss9408&repo=DiplomaCoursework&theme=tokyonight&hide_border=true" alt="Diploma Coursework" />
  </a>
</p>

---

## 📊 GitHub Stats

<p align="left">
  <img src="https://github-readme-stats.vercel.app/api?username=abyss9408&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" alt="GitHub Stats" />
  <img src="https://streak-stats.demolab.com?user=abyss9408&theme=tokyonight&hide_border=true" alt="GitHub Streak" />
</p>
<p align="left">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=abyss9408&layout=compact&theme=tokyonight&hide_border=true&langs_count=8" alt="Top Languages" />
</p>

---

## 📫 Contact

- 💼 [LinkedIn](https://linkedin.com/in/bryanwzang)

---

<p align="center"><i>"The best way to understand a system is to build one yourself."</i></p>
