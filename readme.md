Gamezop AdMob Mediation Adapter for Android (gzp_mediation_adapter)

This repository contains the official Gamezop custom event mediation adapter for Google AdMob. This adapter allows applications to use Gamezop as a third-party ad source within the AdMob mediation stack.

Supported Ad Formats

This adapter supports mediation for the following AdMob ad types:

Banner Ads

Interstitial Ads

Rewarded Ads

Rewarded Interstitial Ads

Native Ads (Barebones integration)

App Open Ads

🚀 Installation

Since this library is distributed via a custom Public Maven Repository hosted on GitHub, you must first configure your project's dependency sources.

Step 1: Configure Project settings.gradle

Open your project's settings.gradle (or settings.gradle.kts) file. You must add the Gamezop Maven repository URL to both the pluginManagement and dependencyResolutionManagement blocks.

This ensures Gradle can find the adapter library.

// In settings.gradle.kts (Kotlin)

pluginManagement {
    repositories {
        google()
        mavenCentral()
        gradlePluginPortal()
        // 1. Repository for plugins
        maven { url = uri("[https://raw.githubusercontent.com/gamezop/gamezop-mediation-releases/main](https://raw.githubusercontent.com/gamezop/gamezop-mediation-releases/main)") }
    }
}

dependencyResolutionManagement {
    // This is the correct location for finding LIBRARIES (dependencies)
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
        
        // 2. Repository for the Gamezop adapter library (REQUIRED)
        maven { url = uri("[https://raw.githubusercontent.com/gamezop/gamezop-mediation-releases/main](https://raw.githubusercontent.com/gamezop/gamezop-mediation-releases/main)") }
    }
}
// ... (rest of the file)


Step 2: Add the Adapter Dependency

Open your app-level build.gradle (or build.gradle.kts) file and add the implementation line to your dependencies block.

dependencies {
    // Required for AdMob SDK
    implementation 'com.google.android.gms:play-services-ads:22.4.0' 
    
    // Add the Gamezop Mediation Adapter
    implementation 'com.gamezop:gzp_mediation_adapter:1.0.0' // Check for the latest version tag
}


Step 3: Sync Project

Click "Sync Project with Gradle Files" in Android Studio to download and integrate the adapter.

🛠️ Usage in AdMob Console

Once the dependency is added, you can configure Gamezop as a mediation source directly in your AdMob account:

Log in to your Google AdMob account.

Navigate to the Mediation group for the app/ad unit.

Add a new Custom Event.

Provide the adapter's class name:

Ad Format

Class Name

All Supported Formats

com.gamezop.ads.GamezopMediationAdapter

Note on Server Parameters: AdMob requires a server parameter (usually labeled 'Parameter' or 'Label'). This parameter should be set to your Gamezop Ad Unit ID.

📦 Publishing New Versions (For Maintainers)

This project uses GitHub Actions to automate publishing the compiled AAR library to the public gamezop-mediation-releases repository.

Update the versionName string in the main module's build.gradle file (e.g., to 1.0.1).

Commit and push the code changes to your main branch.

Go to the repository on GitHub, click "Releases", and Draft a New Release.

The "Tag version" must match the versionName you set (e.g., v1.0.1).

Publish the release. GitHub Actions will automatically build and push the new files to the public Maven repo.