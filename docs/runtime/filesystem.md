# FileSystem

Public file APIs declared in `Runtime/IO/FileSystem.h`.

## Class: `Alice::FileSystem`

### Methods
- `static bool SaveData(const char* filePath, Data& data)`
- `static AliceUInt32 FileSizeOf(const char* path)`
- `static bool CreateDir(std::string path)`
- `static bool CreateFile(std::string path)`
- `static bool MoveFile(const char* srcPath, const char* dstPath)`
- `static bool DeleteDir(std::string path)`
- `static bool DeleteFileWithPath(std::string path)`
- `static bool CopyFile(const char* srcPath, const char* dstPath)`
- `static bool MoveFileToTrash(const char* path)`
- `static bool isDirectoryExist(const std::string& dirPath)`
- `static bool Exists(const char* path)`
- `static bool isAbsolutePath(const std::string& path)`
- `static char* LoadFile(const char* path)`
- `static void CopyDir(const char* src, const char* dst)`
- `static bool LoadDataFromPath(const char* path, Data& data)`

### Windows-only
- `static void GetFiles(LPCTSTR path, LPCTSTR filter, FileItemNode& root)`
- `static void GetFiles(LPCTSTR path, LPCTSTR relativeRootPath, LPCTSTR filter, FileItemNode& root)`
- `static bool DeleteDir(LPCTSTR path)`

## Usage
```cpp
#include "Runtime/IO/FileSystem.h"
#include "Runtime/IO/AliceData.h"
using namespace Alice;

void writeAndRead() {
    Data data(1024);
    data.mDataLen = 3;
    data.mData[0] = 'A'; data.mData[1] = 'B'; data.mData[2] = 'C';
    FileSystem::CreateDir("/tmp/bf");
    FileSystem::SaveData("/tmp/bf/demo.bin", data);

    Data loaded;
    if (FileSystem::LoadDataFromPath("/tmp/bf/demo.bin", loaded)) {
        // use loaded.mData / loaded.mDataLen
    }
}
```

## Notes
- `LoadFile` returns a heap buffer; ensure you free it appropriately.
- Paths should be normalized as needed; see `StringUtils::ToSTDPath`.
