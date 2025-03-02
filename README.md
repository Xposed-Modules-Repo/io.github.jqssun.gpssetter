# GPS Setter

[![LSPosed](https://img.shields.io/github/downloads/Xposed-Modules-Repo/io.github.jqssun.gpssetter/total?label=LSPosed&logo=Android&style=flat&labelColor=F48FB1&logoColor=ffffff)](https://github.com/Xposed-Modules-Repo/io.github.jqssun.gpssetter/releases)
[![stars](https://img.shields.io/github/stars/jqssun/android-gps-setter)](https://github.com/jqssun/android-gps-setter/stargazers)
[![build](https://img.shields.io/github/actions/workflow/status/jqssun/android-gps-setter/apk.yml)](https://github.com/jqssun/android-gps-setter/actions/workflows/apk.yml)
[![release](https://img.shields.io/github/v/release/jqssun/android-gps-setter)](https://github.com/jqssun/android-gps-setter/releases)
[![license](https://img.shields.io/github/license/jqssun/android-gps-setter)](https://github.com/jqssun/android-gps-setter/blob/master/LICENSE)
[![issues](https://img.shields.io/github/issues/jqssun/android-gps-setter)](https://github.com/jqssun/android-gps-setter/issues)
  
A GPS setter based on the Xposed framework. This fork is the first module to achieve support for Android 15+ with its sources available.

[<img src="https://raw.githubusercontent.com/NeoApplications/Neo-Backup/refs/heads/main/badge_github.png" alt="Get it on GitHub" height="80">](https://github.com/jqssun/android-gps-setter/releases)

<!-- 
[![downloads](https://img.shields.io/github/downloads/jqssun/android-gps-setter/total?label=GitHub&logo=GitHub)]()

[<img src="https://fdroid.gitlab.io/artwork/badge/get-it-on.png" alt="Get it on F-Droid" height="80">]()
[<img src="https://gitlab.com/IzzyOnDroid/repo/-/raw/master/assets/IzzyOnDroid.png" height="80">]()
-->

## Motivation

An increasing number of apps are abusing the location permission for tracking purposes, preventing the user from using the app without granting the permission. Traditionally on Android, modifying the response from android server is done using the mock location provider - however, the availability of this feature is device dependent. Additionally, some apps have started explicitly checking for signals regarding whether the location provided is reliable. This module aims to mitigate this by providing an ability to either,
1. hook the app itself to modify the location it receives, or
2. hook the system server if the app explicitly checks for whether itself is being hooked

Specifically, in the case of hooking just the app, it intercepts [`android.location.Location`](https://developer.android.com/reference/android/location/Location) and [`android.location.LocationManager`](https://developer.android.com/reference/android/location/LocationManager) methods including
- [`getLatitude()`](https://developer.android.com/reference/android/location/Location#getLatitude())
- [`getLongitude()`](https://developer.android.com/reference/android/location/Location#getLongitude())
- [`getAccuracy()`](https://developer.android.com/reference/android/location/Location#getAccuracy())
- [`getLastKnownLocation(java.lang.String)`](https://developer.android.com/reference/android/location/LocationManager#getLastKnownLocation(java.lang.String))

## Changes

This module inherits from the original GpsSetter project with the following changes:
- Added support for new location APIs in system server from Android 14+
- Added support for dynamically adjusting the location via a joystick overlay
- Added ability to only depend on FOSS libraries
- Updated UI to work with latest Material Design
- Updated custom designed resource bundles
- Newer dependencies

## Compatibility

- Android 8.1+ (tested up to Android 15)
- Rooted devices with Xposed framework installed (e.g. LSPosed)
- Unrooted devices with LSPatch (with manually embedded specified location)

## Credits

- [Android1500](https://github.com/Android1500/GpsSetter)
- [MapLibre](https://github.com/maplibre/maplibre-native)
- [microG](https://github.com/microg/GmsCore)