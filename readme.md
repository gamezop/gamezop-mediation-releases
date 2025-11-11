# Gamezop AdMob Mediation Adapter for Android (`gzp_mediation_adapter`)

This repository contains the official Gamezop custom event mediation adapter for Google AdMob.  
It allows Android applications to integrate Gamezop as a third-party ad source in Google AdMob mediation.

---

## ✅ Supported Ad Formats

- Banner Ads  
- Interstitial Ads  
- Rewarded Ads  
- Rewarded Interstitial Ads  
- Native Ads (barebones implementation)  
- App Open Ads  

---

## 🚀 Installation

This library is hosted on a custom public Maven repository on GitHub.  
Follow the steps below to integrate it into your project.

---

## Step 1 — Add Maven Repository in `settings.gradle.kts`

```kotlin
pluginManagement {
    repositories {
        google()
        mavenCentral()
        gradlePluginPortal()
        maven { url = uri("https://raw.githubusercontent.com/gamezop/gamezop-mediation-releases/main") }
    }
}

dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
        maven { url = uri("https://raw.githubusercontent.com/gamezop/gamezop-mediation-releases/main") }
    }
}
```
Step 1(b) — Groovy Version (settings.gradle)
```
pluginManagement {
    repositories {
        google()
        mavenCentral()
        gradlePluginPortal()
        maven { url "https://raw.githubusercontent.com/gamezop/gamezop-mediation-releases/main" }
    }
}

dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
        maven { url "https://raw.githubusercontent.com/gamezop/gamezop-mediation-releases/main" }
    }
}
```
Step 2 — Add Dependency (Groovy build.gradle)
```
dependencies {
    implementation 'com.google.android.gms:play-services-ads:22.4.0'
    implementation 'com.gamezop:gzp_mediation_adapter:1.0.0'
}
```
Step 2(b) — Kotlin DSL Version (build.gradle.kts)
```
dependencies {
    implementation("com.google.android.gms:play-services-ads:22.4.0")
    implementation("com.gamezop:gzp_mediation_adapter:1.0.0")
}
```
Step 3 — Sync Project

After adding the dependency, click Sync Project with Gradle Files in Android Studio.

🛠️ AdMob Dashboard Setup

In your AdMob mediation settings:
```
Class Name
com.gamezop.ads.GamezopMediationAdapter

Server Parameter
Your Gamezop Ad Unit ID
```

📦 Publishing New Versions (Maintainers)

Update versionName in the module's build.gradle file.

Commit and push changes.

Open GitHub → Releases → Draft a new release.

Set the tag version matching versionName (example: v1.0.1).

Publish the release.

GitHub Actions will automatically build and upload the Maven artifacts to:

https://github.com/gamezop/gamezop-mediation-releases


---

