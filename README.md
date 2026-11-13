# N-R-AI for Android

N-R-AI is an offline GGUF chat app for Android. The APK contains the application and inference engine; it does not bundle a language model.

## Use

1. Download a compatible `.gguf` model to your Android device (for example, Qwen2-0.5B-Instruct Q8_0).
2. Install and open **N-R-AI**.
3. Tap the model/select button and choose the `.gguf` file from the Android file picker.
4. Wait while the app reads the GGUF metadata, copies the model into its private app storage, and loads it.
5. When loading finishes, type a prompt and send it. After the model is loaded, chatting works offline.

The app keeps a private copy of the selected model inside its app storage. The original model file can remain in Downloads, but do not clear N-R-AI app data if you want to keep the private copy.

## Device notes

- This build uses the upstream llama.cpp Android example and its Arm AI Chat inference library.
- The upstream sample currently requires Android 13 (API 33) or newer; Android 14 is supported.
- Model compatibility depends on the inference library and model architecture. Start with a small GGUF such as Qwen2 0.5B.
- A 0.5B model can still need substantial memory while loading and generating. Close other apps if the device runs low on RAM.
- The first model selection requires enough free storage for a second copy of the GGUF file.

## Build

GitHub Actions builds the APK from the official `ggml-org/llama.cpp` Android sample, applies N-R-AI branding, and uploads the APK as the `N-R-AI-Android-APK` artifact.
