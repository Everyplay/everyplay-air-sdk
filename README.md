Welcome to Everyplay. To get started, make sure you have an account registered, and that you have a unique client ID
for your game. You can get these along with the latest integration instructions at https://developers.everyplay.com/

You can always download the latest SDK upgrades directly from https://github.com/everyplay/everyplay-air-sdk

Looking for iOS version? See https://github.com/everyplay/everyplay-ios-sdk
Looking for Android version? See https://github.com/everyplay/everyplay-android-sdk

Everyplay SDK is licensed under the Apache License, Version 2.0 (http://www.apache.org/licenses/LICENSE-2.0.html) with restrictions. Please see Everyplay Terms of Service at https://everyplay.com/developer-terms-of-service for more information.

Everyplay SDK/AIR - Release Notes
=================================

Adobe AIR and platform specific changes (if any) are separated

## AIR 1830-1140 - Oct 1st 2014

- Now works with -hideAneLibSymbols yes on iOS

### iOS v1.8.3 - Oct 1st 2014 (build 1830)

- Now supports iOS 8 SDK / Xcode6 GM

- Fixed recording support against apps supporting the new
  native resolutions of iPhone 6 and iPhone 6 Plus on iOS 8

- Fixed video player / editor UI to support new iPhone 6 resolutions

- Fixed potential video player seek crash on iOS 8

- iOS 8 fixes for changed Javascript behaviour, fixes social
  network connections

- FaceCam now asks video user permission on iOS 8

- Workaround [UIView layoutSubViews] behaviour on iOS 8:

  Depending on game engine used and how the view handling is implemented,
  transitioning between views may trigger layoutSubViews and during the
  process, re-create OpenGL buffers. In some cases, calling EAGLContext
  renderbufferStorage:fromDrawable fails and may result to frozen graphics

  This is behaviour is mostly seen on some custom engines and cocos2d

- Setting [Everyplay sharedInstance].capture property to nil
  could reset certain default settings to unwanted state, such
  as lowering target video framerate from the default, fixed

### Android v1.1.4 - Oct 1st 2014 (build 1140)

- Video resolution handling improvements

### iOS v1.8.2 - Sep 12th 2014 (build 1820)

- iOS 8 view initialization fixes

- CPU optimizations for games with hard 60fps requirement

- AVFoundation: AVAudioPlayer now supports initWithData: method

- AVFoundation/OpenAL: Backgrounding application during initial splash screen
  could break audio state handling, fixed

## AIR 1810-1130 - Aug 27th 2014

- First public release, please send feedback to support@everyplay.com

- To get started, visit https://developers.everyplay.com/documentation/Everyplay-integration-to-Adobe-Air-game
