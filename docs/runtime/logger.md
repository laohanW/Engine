# Logger

Public logging APIs declared in `Runtime/Debugger/Logger.h`.

## Functions

- `int InitEngineLog(const char *engineLogFilePath)`
- `int FormatCurrDate(char *szTime, char *szDate)`
- `void DebugLog(const char* file, int line, const char* fmt, ...)`
- `void InfoLog(const char* file, int line, const char* fmt, ...)`
- `void ErrorLog(const char* file, int line, const char* fmt, ...)`
- `void EditorErrorLog(const char* file, int line, const char* fmt, ...)`
- `void SetEngineErrorReporter(void(*reporter)(const char* msg))`
- `void ReportEngineError(const char* msg)`

### Macros

- `Debug(f, ...)` (enabled on Windows debug builds)
- `Info(f, ...)`
- `Error(f, ...)`
- `errorC(f, ...)` (editor console)

## Usage

```cpp
#include "Runtime/Debugger/Logger.h"

int main() {
    InitEngineLog("engine.log");
    Info("Engine started: pid=%d", 1234);
    Debug("Loading assets...");
    Error("Non-fatal: %s", "missing optional file");
}
```

## Notes
- `Debug` expands to no-op on non-Windows or non-debug builds.
- Provide a callback via `SetEngineErrorReporter` to surface errors in UIs.
