# KismoEngine

**A deterministic C++ runtime for apps, simulation and games**, built on the Sub0 libraries and
KismoCore. One engine serves several front ends: interactive games, headless batch simulation,
web demos (WASM) and data tooling (Python).

> **Status:** scaffold. The runtime will be seeded from the loop proven in
> [Crucible](https://github.com/CraigHutchinson/Crucible) once a second consumer needs it.

## Scope

| Area | What it provides |
|---|---|
| Loop | Fixed-step, seeded, deterministic simulation with bounded command admission |
| World | ECS world (Sub0ECS), terrain / height-field world model, owned snapshots for presentation |
| Replay | Trace record and replay; full-state parity checks |
| Front ends | Headless scenario runner and exports; render / client adapters; WASM and Python bindings |
| Observation | Bounded diagnostics (Sub0Log) |

Out of scope: any product's game rules, content, models or tuning. Those stay in the consuming
project.

## Where it sits

Design: [platform layering decision](https://github.com/KismoTech/.github/blob/main/docs/decisions/0001-platform-layering.md) · [repository map](https://github.com/KismoTech/.github/blob/main/docs/repositories.md) ·
upstream [Sub0 libraries](https://github.com/CraigHutchinson/.github/blob/main/docs/sub0-family.md).

```text
 products (Kismo products, Crucible, your project)
        │
        ├──► KismoEngine   app · simulation · game runtime      (AGPL-3.0 or commercial)
        ├──► KismoEdge     firmware runtime on Zephyr           (private)
        ▼
   KismoCore              data contracts · records · time · replay · decoders   (MIT)
        │
        ▼
   Sub0 libraries         Sub0Pub · Sub0Log · Sub0Pipeline · Sub0ECS · …
```

## How things get in here

Code is born inside a real consumer and moves here only when a **second consumer** needs it and it
has tests: retain local → improve upstream → extract (with history). There are no speculative
abstractions and no umbrella framework. Consumers pin exact versions.

## Licence

KismoEngine is dual-licensed:

- **Open source:** [AGPL-3.0-only](LICENSE), free for open projects, research and learning.
- **Commercial:** for closed products, private modifications, or hosted services without AGPL
  obligations. See [COMMERCIAL-LICENSE.md](COMMERCIAL-LICENSE.md) and open a
  "Commercial License Request" issue.

See [NOTICE](NOTICE) and [CONTRIBUTING.md](CONTRIBUTING.md) for contribution terms.
