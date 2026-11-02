# Çağan Özcan

iOS · Unreal Engine 5 / VR · AI integration — I build and ship products end to end.

Eskişehir, Türkiye · English C1 · Japanese B2 · Open to relocation (Netherlands / Tokyo) and remote roles
📧 caganozcan59@outlook.com · [LinkedIn](https://www.linkedin.com/in/%C3%A7a%C4%9Fan-%C3%B6zcan-3ab10935b/)

---

## Shipped products

### PediX Y-Site — paid clinical reference app, App Store
[App Store](https://apps.apple.com/tr/app/pedix-y-site/id6758942289) · Swift · SwiftUI · RevenueCat · Fastlane · Python/PyMuPDF

Pediatric nurses use it mid-shift to check Y-site compatibility of IV drugs: 418 drugs, 87,000+ pairs, result in under two seconds.

- Solo developer: product, data, iOS app, subscriptions, App Store release, marketing.
- Built the data pipeline that extracts and structures compatibility data from clinical references (Stabilis, hospital handbooks), then had physicians review it.
- 14-day trial → monthly subscription (RevenueCat), active paying users.
- Wrote a B2B sales programme for private hospital chains in Turkey: tiered licensing, free pilot, Apple Search Ads.

### MedikalVR — Unreal Engine 5 medical training simulation, Meta Quest 3
Unreal Engine 5 · Blueprint · OpenXR · MetaHuman · Whisper · GPT-4o · ElevenLabs

A VR patient you can actually talk to. Built for a client (BD Medikal) as a clinical-communication trainer.

- Real-time voice loop: **Whisper (STT) → GPT-4o (dialogue + emotion detection) → ElevenLabs (TTS)**, streamed so the MetaHuman answers without breaking immersion.
- SPIKES-protocol scoring: the simulation grades how the clinician delivers bad news, stage by stage.
- Full lifecycle: architecture, Blueprint logic, NPC animation, procedural behaviour, demo approved by the client's physicians.

### Freelance web
Next.js · Vercel · iyzico · Paraşüt API · n8n

E-commerce payment integration and automated invoicing for two specialty coffee brands; a retainer-based small-business site with hosting, maintenance and blog.

---

## Open source — Unleashed Recompiled (Apple ports)

Systems-level C++ / Metal work on the Sonic Unleashed static recompilation, used by the community:

- [iOS build — experimental IPA](https://github.com/yorgunkral31/UnleashedRecomp/releases/tag/ios-20261031): launches on iOS 27 with the UIScene lifecycle, fills the screen in landscape, survives lock/unlock and app switching, up to 120 FPS (ProMotion) on iPhone 16 Pro. Built on the port by [@Markos-Th09](https://github.com/Markos-Th09).
- [macOS build (Apple Silicon, native Metal)](https://github.com/yorgunkral31/UnleashedRecomp/releases/tag/metal-20260920), on top of the native Metal backend by [@squidbus](https://github.com/squidbus).

Root-cause fixes on the iOS port, each found on device from crash reports and traces:

- **Crash on every second unlock.** The suspend path drained the GPU after the frame's command list was already open, and the drain submits command list 0, so a frame suspended at index 0 resumed into a closed list and crashed in the driver. Moved the drain before the list is begun; verified over 21 lock/unlock cycles. ([commit](https://github.com/yorgunkral31/UnleashedRecomp/commit/073a6b3))
- **Image squashed into half the screen.** Measured the view hierarchy on device: SDL's Metal view stayed at its portrait launch size because UIKit never resizes a swapped-in root view. ([commit](https://github.com/yorgunkral31/UnleashedRecomp/commit/29140b6))
- **Suspend/resume freezes and watchdog kills**, a boot deadlock, and missing game-specific shader logic in the cross-compiled shader recompiler. ([findings](https://github.com/hedge-dev/UnleashedRecomp/pull/1767))

Upstream:

- ProMotion support landed in [Markos-Th09/UnleashedRecomp-iOS](https://github.com/Markos-Th09/UnleashedRecomp-iOS/commit/06026b1) and [Markos-Th09/plume#1](https://github.com/Markos-Th09/plume/pull/1).
- Crash report and patch for [plume](https://github.com/renderbag/plume/pull/115)'s Metal backend on iOS, landed via [#116](https://github.com/renderbag/plume/pull/116).

## How I work

Claude Code + MCP tooling daily, specs before code, tests as the pass/fail gate for anything an agent generates. I own every line that ships.

## Stack

| | |
|---|---|
| iOS | Swift, SwiftUI, UIKit, Xcode, RevenueCat, App Store Connect, Fastlane |
| Game / VR | Unreal Engine 5, Blueprint, Meta Quest 3, OpenXR, MetaHuman |
| AI | OpenAI API (GPT-4o, Whisper), ElevenLabs, NeoStack AI, n8n, MCP, Claude Code |
| Web | Next.js, TypeScript, Vercel, iyzico, Paraşüt API |
| Other | Python, PyMuPDF, Git, Figma |

Currently: Associate's in Web Design & Coding, Anadolu University (bachelor's transfer planned). Nominated team member, Alumni UK grant application 2026–27.
