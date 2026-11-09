# Engine notes — Unreal Engine

Support level: **partial**

Build from the .uproject with the Android toolchain (NDK r25+, ASTC/ETC2 textures) using UnrealBuildTool -platform Android.

## Requirements

- The .uproject source project and its Content/ folder
- Unreal Engine source or the matching engine install with Android support
- Android NDK, SDK and JDK versions supported by that engine release
- Shader assets cooked for Android (ASTC/ETC2)

## Detected evidence

- Binary contains “bUE5b”
