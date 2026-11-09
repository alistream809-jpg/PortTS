# Native runtime integration — Unreal Engine

This host project packages assets, verifies them and applies the size plan. The engine runtime
itself is produced by the engine's own Android export, so the game will start only once those
libraries are added.

## Expected libraries (arm64-v8a)

- `libUnreal.so`
- `libUE4.so`
- `libmain.so`

Place them in:

```
android/app/src/main/jniLibs/arm64-v8a/
```

## Recommended flow

1. Export an Android build from the engine: Build from the .uproject with the Android toolchain (NDK r25+, ASTC/ETC2 textures) using UnrealBuildTool -platform Android.
2. Copy this project's `android/app/src/main/assets/` content and `app/build.gradle`
   packaging settings into the exported module, or copy the exported libraries into
   `jniLibs/arm64-v8a/` here if your engine supports a content-only export.
3. Unreal's Android build is produced by UnrealBuildTool. This project carries the asset plan and packaging settings for that build.

NeepPort does not generate placeholder runtime libraries: a build without the real engine
runtime is not a working game, and the app refuses to present it as one.
