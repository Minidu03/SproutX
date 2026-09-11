# SproutX — Android (Kotlin + Jetpack Compose)

Smart cultivation companion for Sri Lankan farmers: biometric farmer registration,
satellite farm monitoring, AI crop disease diagnosis (Gemini vision), monsoon-aware
dashboard, and nearest collection centers.

## Before you build
1. Open this folder in Android Studio (Koala/Ladybug or newer).
2. Get a **Google Maps SDK for Android** API key and paste it into
   `app/src/main/AndroidManifest.xml` → `com.google.android.geo.API_KEY`.
3. Get a **Gemini API key** (Google AI Studio) and paste it into
   `GeminiDiagnosisService.kt` → `GEMINI_API_KEY`
   (swap the endpoint for your own backend proxy if you don't want the key on-device).
4. Sync Gradle, then Run on an emulator (Pixel, API 33+ recommended, with Google Play
   services image) or a physical device.

## Notes
- Farmer profile + diagnosis history persist locally via Jetpack DataStore.
- Biometric enrollment uses `androidx.biometric` (fingerprint/face, whatever the
  device supports) — the Android equivalent of Face ID/Touch ID.
- Photo capture (profile + crop scan) uses CameraX with a live preview.
- Everything is wired with mock/sample data where a real backend isn't specified
  (weather, farm metrics) — swap `FarmMetricsRepository` for a real API when ready.
