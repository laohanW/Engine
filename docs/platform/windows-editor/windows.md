# Editor Windows: Hierarchy, Inspector, Project, Scene

## Common Pattern
Each window exposes:
- `void Init(BaseWindow* parent)`
- `ViewWindow* GetViewWindow()`
- `static <Window>* Singleton()`

## HierarchyWindow
Header: `Platform/Windows/Editor/HierarchyWindow/HierarchyWindow.h`

## InspectorWindow
Header: `Platform/Windows/Editor/InspectorWindow/InspectorWindow.h`

## ProjectWindow
Header: `Platform/Windows/Editor/ProjectWindow/ProjectWindow.h`

## SceneWindow
Header: `Platform/Windows/Editor/SceneWindow/SceneWindow.h`

## Usage
```cpp
#include "Platform/Windows/Editor/HierarchyWindow/HierarchyWindow.h"
#include "Platform/Windows/Editor/InspectorWindow/InspectorWindow.h"
#include "Platform/Windows/Editor/ProjectWindow/ProjectWindow.h"
#include "Platform/Windows/Editor/SceneWindow/SceneWindow.h"
using namespace Editor;

void setup(BaseWindow* parent) {
    HierarchyWindow::Singleton()->Init(parent);
    InspectorWindow::Singleton()->Init(parent);
    ProjectWindow::Singleton()->Init(parent);
    SceneWindow::Singleton()->Init(parent);
}
```
