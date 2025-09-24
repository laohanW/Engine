# StringUtils and FixedString

Public string APIs declared in `Runtime/String/StringUtils.h` and `Runtime/String/FixedString.h`.

## Class: `Alice::StringUtils`

### UTF Conversions
- `static int UTF8ToUTF32(const unsigned char* src, int len, UTF32Char* dst)`
- `static int UTF8ToUTF32(const unsigned char* src, int len, AliceUInt32* dst)`
- `static bool UTF32ToUTF8(const AliceUInt32* src, int len, unsigned char* dst)`
- `static bool UTF32CharToUTF8(const AliceUInt32 src, unsigned char* dst, int& len)`
- `static bool UTF32CharToUTF16(const char32_t u32Ch, AliceSInt16* u16Ch)`

### Path Helpers
- `static const char* GetFileExtensionFromPath(const char* path)`
- `static void GetDirFromFullPath(const char* path, char* dir)`
- `static void TrimFileExtension(char* path)`
- `static void GetFileNameWithOutExtension(const char* path, char* name)`
- `static void ToSTDPath(char* path)` / `ToLuaPath`, `LuaPathToSTDPath`, `ToWindowsPath`

### String Helpers
- `static void TrimStart(char* original, const char* startToTrim)`
- `static void TrimEnd(char* original, const char* endToTrim)`
- `static bool EndWith(const char* original, const char* end)`
- `static bool EndWithI(const char* original, const char* end)`
- `static bool StartWith(const char* original, const char* start)`
- `static void SplitPathToComponent(char* path, std::vector<std::string>& components)`
- `static int GetNextPosOf(const char* buffer, int len, char c)`
- ... and URL encode/decode helpers

## Class: `Alice::FixedString`

- Dynamic small string owning a mutable buffer.
- Key methods: `Resize`, `Set`, comparisons, append (`operator<<`), copy-out (`operator>>`), trimming, path conversions.

## Usage
```cpp
#include "Runtime/String/StringUtils.h"
#include "Runtime/String/FixedString.h"
using namespace Alice;

void normalize() {
    char path[256] = "Assets\\Textures\\icon.png";
    StringUtils::ToSTDPath(path); // -> Assets/Textures/icon.png
    FixedString fs;
    fs = path;
    fs.TrimExtension(); // -> Assets/Textures/icon
}
```
