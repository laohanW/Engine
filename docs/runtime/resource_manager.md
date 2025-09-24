# ResourceManager

Public resource APIs declared in `Runtime/IO/ResourceManager.h`.

## Class: `Alice::ResourceManager`

### External (outer) file APIs
- `static bool Exist(const char* path)`
- `static bool DeleteFileWithPath(const char* path)`
- `static bool CreateDir(const char* path)`
- `static bool DeleteDir(const char* path)`
- `static void CopyInternalFileOut(const char* internalPath)`

### Internal/builtin data APIs
- `static bool ExistInternal(const char* path)`
- `static bool LoadInternalData(const char* path, Data& data)`
- `static bool RenameInternalFileName(const char* srcFile, const char* dstFile)`
- `static bool DeleteInternalFile(const char* targetFile)`
- `static bool CopyFileToInternal(const char* targetFile, const char* dstFile)`
- `static bool MoveInternalFile(const char* srcFile, const char* dstFile)`
- `static bool SaveInternalData(const char* targetPath, Data& data)`
- `static bool CreateInternalFile(const char* targetPath)`

### Unified loader
- `static bool LoadOuterData(const char* path, Data& data)`
- `static bool LoadBuiltinData(const char* path, Data& data)`
- `static bool LoadData(const char* path, Data& data, FixedString* realPath = nullptr)`

### Initialization and Paths
- `static void Init()`
- `static FixedString* mAssetsDir`
- `static FixedString* mDataDir`
- `static FixedString* mDocumentDir`
- `static FixedString* mDesktopDir`

## Usage
```cpp
#include "Runtime/IO/ResourceManager.h"
#include "Runtime/IO/AliceData.h"
#include "Runtime/String/FixedString.h"
using namespace Alice;

void loadAsset() {
    ResourceManager::Init();
    Data data;
    FixedString realPath;
    if (ResourceManager::LoadData("Assets/config.json", data, &realPath)) {
        // realPath contains resolved physical path, if provided
    }
}
```

## Notes
- Use `LoadData` to transparently search runtime, builtin, or external paths.
- Manage `Data` lifetime properly; it owns its buffer and frees in destructor.
