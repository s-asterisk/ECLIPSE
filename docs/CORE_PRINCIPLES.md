# ECLIPSE Foundational Principles

## Non-Negotiable Tenets
1. **Fidelity Over Performance**: Cycle-accurate emulation before optimization
2. **Zero-Cost Access**: Always free for education and open-source use
3. **Python-First Extensibility**: Native CPython > IronPython/Lua
4. **Hardware Truthfulness**: Analog characteristics matter as much as digital

## Architectural Pillars
```plantuml
@startuml
package "Simulation Core" {
  [QEMU] as qemu
  [Analog Modeling] as analog
  [Plugin Runtime] as plugins
}

package "User Experience" {
  [Qt Designer] as designer
  [Python Console] as py
  [Collaboration] as collab
}

qemu --> designer : Telemetry
plugins --> py : API Surface
analog --> qemu : Signal Injection
collab --> designer : Session Sync
@enduml
