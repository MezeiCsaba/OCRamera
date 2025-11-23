# OCR Kamera - Android Alkalmazás

Ez egy Android alkalmazás, amely a kamerát használva fényképet készít, és a Google ML Kit Text Recognition API segítségével felismeri és kiírja a képen található számokat.

## Funkciók

- 📷 **Kamera előnézet**: Valós idejű kamera preview
- 🔢 **Szám felismerés**: Automatikus OCR a képeken található számok kinyeréséhez
- 📱 **Modern UI**: Material Design 3 alapú felhasználói felület
- 🎯 **Egyszerű használat**: Egy gombnyomással készíthetsz képet és kinyerheted a számokat

## Technológiák

- **CameraX**: Modern kamera API a fényképek készítéséhez
- **ML Kit Text Recognition**: Google ML Kit offline szövegfelismerés
- **Material Design 3**: Modern és elegáns UI komponensek
- **AndroidX**: Legújabb Android support library-k

## Követelmények

- **Minimum SDK**: Android 5.0 (API 21)
- **Target SDK**: Android 14 (API 34)
- **Engedélyek**: Kamera hozzáférés

## Telepítés és Futtatás

### Android Studio-val

1. Nyisd meg a projektet Android Studio-ban
2. Várj, amíg a Gradle sync befejeződik
3. Csatlakoztass egy Android eszközt vagy indíts el egy emulátort
4. Kattints a "Run" gombra (▶️)

### Gradle parancssorból

```bash
# Windows
gradlew.bat assembleDebug

# Linux/Mac
./gradlew assembleDebug
```

Az APK fájl itt található: `app/build/outputs/apk/debug/app-debug.apk`

## Használat

1. **Indítsd el az alkalmazást**
2. **Engedélyezd a kamera hozzáférést** amikor kéri
3. **Irányítsd a kamerát** egy számokat tartalmazó objektumra (pl. óra, számológép, könyv oldalszám)
4. **Nyomd meg a kamera gombot** (lila lebegő gomb)
5. **Az eredmény megjelenik** az alsó kártyán

## Projekt Struktúra

```
android-ocr-camera-app/
├── app/
│   ├── build.gradle                 # App szintű Gradle konfiguráció
│   ├── proguard-rules.pro          # ProGuard szabályok
│   └── src/
│       └── main/
│           ├── AndroidManifest.xml  # App manifest és engedélyek
│           ├── java/com/example/ocrcamera/
│           │   └── MainActivity.java # Fő activity
│           └── res/
│               ├── layout/
│               │   └── activity_main.xml  # UI layout
│               ├── values/
│               │   ├── colors.xml         # Színek
│               │   ├── strings.xml        # Szövegek (magyar)
│               │   └── themes.xml         # Material téma
│               └── xml/
│                   ├── backup_rules.xml
│                   └── data_extraction_rules.xml
├── build.gradle                     # Projekt szintű Gradle
├── settings.gradle                  # Gradle beállítások
└── gradle.properties               # Gradle tulajdonságok
```

## Főbb Komponensek

### MainActivity.java

A fő activity, amely kezeli:
- Kamera engedélyek kérését
- CameraX inicializálást és lifecycle-t
- Fénykép készítést
- ML Kit Text Recognition integrációt
- Számok kinyerését regex-szel
- Eredmény megjelenítését

### activity_main.xml

Modern Material Design layout:
- `PreviewView`: Kamera előnézet
- `FloatingActionButton`: Fénykép készítés gomb
- `MaterialCardView`: Eredmény megjelenítő kártya

## Függőségek

```gradle
// AndroidX Core
androidx.core:core:1.12.0
androidx.appcompat:appcompat:1.6.1
com.google.android.material:material:1.11.0

// CameraX
androidx.camera:camera-core:1.3.1
androidx.camera:camera-camera2:1.3.1
androidx.camera:camera-lifecycle:1.3.1
androidx.camera:camera-view:1.3.1

// ML Kit
com.google.mlkit:text-recognition:16.0.0
```

## Hibaelhárítás

### Kamera nem indul el
- Ellenőrizd, hogy megadtad-e a kamera engedélyt
- Győződj meg róla, hogy az eszközödön van kamera
- Próbáld újraindítani az alkalmazást

### Nem ismer fel számokat
- Győződj meg róla, hogy a számok jól láthatóak és fókuszban vannak
- Próbálj jobb fényviszonyokat biztosítani
- A kézzel írott számok felismerése nehezebb lehet

### Gradle sync hiba
- Ellenőrizd az internet kapcsolatot
- Próbáld meg: File → Invalidate Caches / Restart
- Frissítsd az Android Studio-t a legújabb verzióra

## Licenc

Ez a projekt oktatási célokra készült.

## Szerző

Készítette: Csaba Mezei (supported by Antigravity AI Assistant)
