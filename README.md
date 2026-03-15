# Ben 10: Ultimate Alien Multiverse — Multiplayer Unity Game
## Computer Graphics Course Project Plan (6–8 Weeks, 5-Person Team)

---

## 🎯 Project Overview

**Goal:** Build a 3D multiplayer arena-brawler inspired by Ben 10: Ultimate Alien. Players select from Ben 10 aliens, fight in themed arenas, and compete online using Unity's multiplayer stack.

**Engine:** Unity 2022 LTS (or Unity 6)  
**Multiplayer SDK:** Mirror Networking (free, open-source, production-tested)  
**Version Control:** Git + GitHub (existing repo)  
**Target Platform:** Windows PC (standalone build)  
**Course Focus:** Computer Graphics principles — shaders, lighting, particle effects, post-processing, 3D modelling integration

---

## 👥 Team Roles & Responsibilities

| # | Role | Member | Responsibilities |
|---|------|--------|-----------------|
| 1 | **Project Lead / Gameplay Programmer** | Member 1 | Architecture decisions, player controller, alien ability system, sprint coordination |
| 2 | **Graphics / Shader Programmer** | Member 2 | Custom shaders (HLSL/ShaderGraph), post-processing (URP), lighting, visual effects — **primary CG deliverable** |
| 3 | **Networking Programmer** | Member 3 | Mirror setup, lobby, player sync, lag compensation, game state management |
| 4 | **3D Artist / Animator** | Member 4 | Alien character models, arena environments, animations, rigging (Blender → Unity) |
| 5 | **UI/UX + Audio Designer** | Member 5 | HUD, menus, health bars, character select screen, SFX, music integration |

> **Note:** Roles overlap during crunch weeks. Everyone contributes to bug fixing in Weeks 6–7.

---

## 🗓️ Sprint Schedule

### **Week 1 — Foundation & Setup**
**Goal:** Everyone can open the project, build it, and see a placeholder scene.

| Task | Owner |
|------|-------|
| Set up Unity project with URP, Mirror, folder structure | Lead |
| Configure Git branching strategy (`main`, `develop`, feature branches) | Lead |
| Create base `PlayerController` (movement, jumping, basic attack) | Lead |
| Research + sketch alien designs; import or create placeholder meshes | Artist |
| Set up Mirror `NetworkManager`, simple host/join flow | Networking |
| Create `tokens.css`-equivalent: Unity Material Design System doc, define a color palette | Graphics |
| Prototype HUD canvas with health bar and ability cooldown slots | UI/UX |

**Milestone ✅ Week 1:** Players can move in a shared scene over LAN.

---

### **Week 2 — Core Systems**
**Goal:** Alien selection, basic combat, and first arena block-out.

| Task | Owner |
|------|-------|
| Implement `AlienAbilitySystem` — 3 base aliens with unique abilities (e.g., Heatblast, Four Arms, XLR8) | Lead |
| Begin arena block-out in Blender (Cosmic Codon Stream, Mt. Rushmore themed) | Artist |
| Sync player position/animation over network with lag compensation | Networking |
| Build `CharacterSelectScene` with alien previews | UI/UX |
| Start **custom ShaderGraph shaders** for each alien (Heatblast = fire dissolve shader, XLR8 = speed lines) | Graphics |
| Implement transformation VFX (Omnitrix glow, dial spin particle system) | Graphics |

**Milestone ✅ Week 2:** 2 players can select different aliens and fight in the same scene.

---

### **Week 3 — Graphics Deep Dive (CG Focus Week)**
**Goal:** Fulfill the core Computer Graphics requirements with demonstrable visual systems.

| Task | Owner |
|------|-------|
| **Toon/Cel shading shader** (signature Ben 10 look) — ShaderGraph + HLSL custom node | Graphics |
| **Real-time lighting:** Dynamic point lights tied to alien abilities (Heatblast emits light) | Graphics |
| **Post-processing stack:** Bloom, Chromatic Aberration, Depth of Field, Color Grading | Graphics |
| **Particle systems:** Fire, lightning, speed trails, energy blasts | Graphics + Lead |
| Animate 3 aliens (idle, run, attack, hit, death) | Artist |
| Import arena into Unity, add collision, set up NavMesh-free zone layout | Artist |
| Network: implement health sync, death/respawn logic | Networking |

**Milestone ✅ Week 3:** Game looks visually distinct with cartoon shading and VFX — showcase-ready screenshots.

---

### **Week 4 — Gameplay Completion**
**Goal:** All 5 aliens playable, full game loop working (round start → fight → win screen).

| Task | Owner |
|------|-------|
| Add remaining 2 aliens: Diamondhead, Big Chill (abilities + models + shaders) | Lead + Artist |
| Implement score/round system: first to 3 kills wins | Lead |
| Networked lobby: room creation, player list, ready button, alien lock-in | Networking |
| Win/Loss screen with stats (kills, damage dealt) | UI/UX |
| Add interactive environment: destructible crates, moving platforms (networked) | Lead + Networking |
| Arena polish: textures, PBR materials, skybox, ambient occlusion | Artist + Graphics |

**Milestone ✅ Week 4:** Full game loop playable end-to-end with 2 players.

---

### **Week 5 — Polish & Content Expansion**
**Goal:** Feel and juice — the game should be fun and visually impressive.

| Task | Owner |
|------|-------|
| Camera: dynamic zoom-out when players are far apart (like Smash Bros) | Lead |
| Sound design: alien SFX library, ambient arena sounds, UI sounds | UI/UX |
| Integrate Ben 10 themed music or original synthwave tracks | UI/UX |
| Add screen-space effects on hit (screen shake, flash) | Graphics |
| Optimize shaders — profile with Unity Frame Debugger, fix overdraw | Graphics |
| Second arena (optional stretch): Null Void Prison themed level | Artist |
| Network stress test: latency simulation, 3–4 player test | Networking |

**Milestone ✅ Week 5:** Game is fun to play and visually polished.

---

### **Week 6 — Integration & Bug Fixing**
**Goal:** Merge all branches, eliminate bugs, prepare for demo.

| Task | Owner |
|------|-------|
| Full integration merge from all feature branches → `develop` | Lead |
| Bug bash session (all 5 members play and log issues) | All |
| Fix top 10 critical bugs | All (distributed) |
| Profile and optimize: target 60fps on mid-range hardware | Lead + Graphics |
| Build Windows `.exe` and test on multiple machines | Lead |
| Write in-game tutorial / control overlay | UI/UX |

**Milestone ✅ Week 6:** Stable, buildable game runs at 60fps.

---

### **Week 7 — Demo Prep & Documentation** *(if 7-week schedule)*
**Goal:** Presentation-ready deliverables.

| Task | Owner |
|------|-------|
| Record gameplay trailer / demo video | Lead |
| Write technical report sections (each owns their section) | All |
| Create poster / slide deck highlighting CG techniques used | Graphics + UI/UX |
| Final QA and edge-case fixes | All |

---

### **Week 8 — Buffer / Stretch Goals** *(if 8-week schedule)*
**Goal:** Extra polish or stretch features.

| Stretch Goals | Owner |
|---------------|-------|
| 4-player support | Networking |
| Third arena | Artist |
| Omnitrix unlock progression | Lead |
| Ray-traced reflections (DXR) for high-end machines | Graphics |

---

## 🏗️ Technical Architecture

```
Ben10-Ultimate-Alien-Multiverse/
├── Assets/
│   ├── _Project/
│   │   ├── Scripts/
│   │   │   ├── Gameplay/
│   │   │   │   ├── PlayerController.cs
│   │   │   │   ├── AlienAbilitySystem.cs
│   │   │   │   ├── AlienData.cs (ScriptableObject)
│   │   │   │   └── Aliens/
│   │   │   │       ├── HeatblastAbilities.cs
│   │   │   │       ├── XLR8Abilities.cs
│   │   │   │       └── ...
│   │   │   ├── Networking/
│   │   │   │   ├── NetworkGameManager.cs
│   │   │   │   ├── LobbyManager.cs
│   │   │   │   └── PlayerNetworkSync.cs
│   │   │   ├── UI/
│   │   │   │   ├── HUDController.cs
│   │   │   │   ├── CharacterSelectUI.cs
│   │   │   │   └── LobbyUI.cs
│   │   │   └── Audio/
│   │   │       └── AudioManager.cs
│   │   ├── Shaders/
│   │   │   ├── ToonShader.shadergraph
│   │   │   ├── FireDissolve.shadergraph
│   │   │   ├── SpeedLines.shadergraph
│   │   │   └── IceRim.shadergraph
│   │   ├── Materials/
│   │   ├── Prefabs/
│   │   │   ├── Aliens/
│   │   │   └── VFX/
│   │   ├── Scenes/
│   │   │   ├── MainMenu.unity
│   │   │   ├── CharacterSelect.unity
│   │   │   ├── Arena_CodonStream.unity
│   │   │   └── Arena_NullVoid.unity
│   │   └── Art/
│   │       ├── Models/
│   │       ├── Textures/
│   │       └── Animations/
│   └── ThirdParty/
│       └── Mirror/
```

---

## 🖥️ Computer Graphics Requirements Coverage

| CG Concept | Implementation in Game |
|------------|----------------------|
| **Shaders (HLSL/ShaderGraph)** | Toon cel shader, fire dissolve, speed-line effect, ice rim light |
| **Lighting Models** | Phong/Blinn-Phong in custom shader nodes; point lights from abilities |
| **Particle Systems** | Fire, lightning arcs, energy blast trails, transformation sparkles |
| **Post-Processing** | Bloom (energy glow), Chromatic Aberration (hit flash), Color Grading |
| **Texturing** | UV mapping, Normal maps, Emission maps for glow effects |
| **Animation** | Skeletal rigging, blend trees (idle/run/attack), IK for grounding |
| **Camera Systems** | Dynamic orthographic zoom, screen shake, depth of field |
| **PBR Materials** | Arena environments using URP Lit shader with metallic/roughness |

---

## 🌿 Git Branching Strategy

```
main          ← stable releases / demo builds only
  └── develop ← integration branch
        ├── feature/gameplay-core      (Member 1)
        ├── feature/graphics-shaders   (Member 2)
        ├── feature/networking         (Member 3)
        ├── feature/art-assets         (Member 4)
        └── feature/ui-audio           (Member 5)
```

- **Merge to `develop`** via Pull Request with 1 reviewer approval
- **Merge to `main`** only at milestone checkpoints (Weeks 2, 4, 6)
- Use Git LFS for large assets (`.fbx`, `.png`, textures)

---

## 📦 Alien Roster

| Alien | Abilities | Shader Effect | Difficulty |
|-------|-----------|---------------|-----------|
| **Heatblast** | Fireball, Fire AOE, Flame Dash | Fire dissolve + emission glow | Medium |
| **Four Arms** | Ground slam, Boulder throw, Super grab | Standard toon + dust VFX | Easy |
| **XLR8** | Dash strike, Tornado spin, Speed trap | Speed lines trail shader | Medium |
| **Diamondhead** | Crystal shards, Shield, Crystal prison | Refraction/prism shader | Hard |
| **Big Chill** | Freeze ray, Ice wall, Phase through | Frost rim light + freeze shader | Hard |

---

## ⚠️ Risks & Mitigations

| Risk | Likelihood | Mitigation |
|------|-----------|------------|
| Networking complexity spikes | High | Use Mirror's built-in examples; prototype early in Week 1 |
| Art assets take too long | Medium | Use free asset store packs as placeholders; replace iteratively |
| Merge conflicts in Unity scenes | High | Lock scenes to one owner per week; use prefab-based workflow |
| Performance drops from shaders | Medium | Profile weekly with Frame Debugger; shader LOD fallbacks |
| Scope creep | High | Lock feature set at end of Week 4; extras go to Week 8 backlog |

---

## 📋 Weekly Standup Format

Every session (or every 2 days async via Discord):
1. **What did I finish?**
2. **What am I doing next?**
3. **Any blockers?**

Use a shared **Trello / Notion board** or **GitHub Projects** to track task status.

---

## 🏆 Final Deliverables

- [ ] Playable Windows `.exe` build (2-player minimum)
- [ ] Technical Report (each member documents their subsystem)
- [ ] Gameplay Demo Video (2–3 min showcase)
- [ ] Slide Deck / Poster highlighting CG techniques
- [ ] GitHub repository with clean commit history
- [ ] Shader documentation (screenshots + explanations for CG course)
