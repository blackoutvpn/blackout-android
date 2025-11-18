# Blackout VPN for Android

This is the official Android client for **Blackout VPN**, a lightweight, private, no-logs VPN powered by modern WireGuard tunnels.  
No analytics. No tracking. Just a fast encrypted tunnel.

## Building

    $ git clone https://github.com/blackoutvpn/blackout-android
    $ cd blackout-android
    $ ./gradlew assembleRelease

The generated APK will be located under:

    ui/build/intermediates/apk/

macOS users may need [`flock(1)`](https://github.com/discoteq/flock).

## Embedding

The underlying tunnel engine comes from the official WireGuard project and is available on Maven Central:

    implementation 'com.wireguard.android:tunnel:$wireguardTunnelVersion'

Enable Java 17 + desugaring if embedding the tunnel code:

    compileOptions {
        sourceCompatibility JavaVersion.VERSION_17
        targetCompatibility JavaVersion.VERSION_17
        coreLibraryDesugaringEnabled = true
    }
    dependencies {
        coreLibraryDesugaring "com.android.tools:desugar_jdk_libs:2.0.3"
    }

## Notes

Blackout VPN does not collect logs, analytics, crash reports, or any user-identifying data.  
This client supports both userspace and kernel-accelerated WireGuard backends where available.

