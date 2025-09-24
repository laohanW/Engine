# EditorMainWindow

Declares `Editor::EditorMainWindow` in `Platform/Windows/Editor/EditorMainWindow.h`.

## Public Methods
- `void Init()`

## Event Hooks (protected)
- `OnLButtonDown`, `OnLButtonUp`, `OnMouseMove`, `OnMouseLeave`
- `OnKeyDown`, `OnKeyUp`, `OnChar`, `OnIMEChar`, `OnCompositionIMEString`
- `OnMouseWheel`, `OnSize`, `OnCommand`
- `InitSubWindows`

## Members
- `HACCEL mAccel`

## Usage
```cpp
#include "Platform/Windows/Editor/EditorMainWindow.h"
using namespace Editor;

void startEditor() {
    EditorMainWindow wnd;
    wnd.Init();
}
```
