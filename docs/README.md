# BattleFire Engine Documentation

Welcome to the BattleFire Engine documentation. This site covers public APIs, components, and usage examples for engine runtime and the Windows Editor.

- Runtime API Reference: files under `Runtime/`
- Editor Components: files under `Platform/Windows/Editor/`

## Getting Started

- Build prerequisites: CMake 3.18+, a C++17 compiler, and platform SDKs.
- Quick compile (from repo root):
  1. `mkdir build && cd build`
  2. `cmake ..`
  3. `cmake --build .`

## Documentation Structure

- `runtime/`: High-level guides and examples for core runtime APIs (I/O, strings, memory, containers)
- `platform/windows-editor/`: Editor windows and UI components

## Examples

See each API page for concrete examples. Common snippets:

```cpp
#include "Runtime/Debugger/Logger.h"

int main() {
    InitEngineLog("engine.log");
    Info("BattleFire started");
    return 0;
}
```

```cpp
#include "Runtime/IO/ResourceManager.h"
#include "Runtime/IO/AliceData.h"
using namespace Alice;

void load() {
    Data data;
    if (ResourceManager::LoadData("Assets/example.bin", data)) {
        // use data.mData / data.mDataLen
    }
}
```
