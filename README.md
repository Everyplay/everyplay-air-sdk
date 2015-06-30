Welcome to Everyplay. To get started, make sure you have an account registered, and that you have a unique client ID
for your game. You can get these along with the latest integration instructions at https://developers.everyplay.com/

You can always download the latest SDK upgrades directly from https://github.com/everyplay/everyplay-air-sdk

Looking for iOS version? See https://github.com/everyplay/everyplay-ios-sdk
Looking for Android version? See https://github.com/everyplay/everyplay-android-sdk

Everyplay SDK is licensed under the Apache License, Version 2.0 (http://www.apache.org/licenses/LICENSE-2.0.html) with restrictions. Please see Everyplay Terms of Service at https://everyplay.com/developer-terms-of-service for more information.

Everyplay SDK/AIR - Release Notes
=================================

Adobe AIR and platform specific changes (if any) are separated

## AIR 1980-1400 - Jun 30th 2015

- Removed setThumbnailWidth method from wrapper API

- Removed onEveryplayThumbnailReadyAtFilePath from wrapper IEveryplayListener

### iOS v1.9.8 - Jun 29th 2015 (build 1980)

- Now allows 60fps recordings on iOS 8+ devices with
  A7 CPU or later (devices with 64bit capability)

  To change the target framerate from the default 30fps, call
  [[Everyplay sharedInstance] capture].targetFPS

- Metal: CPU performance and snapshotRenderbuffer improvements

- Live FaceCam: When the internal preview box is hidden and
  a target texture is in use, the video content is no longer
  encoded to a separate file and doesn't show separately in
  the video player

- Removed thumbnailWidth property from EveryplayCapture

- Removed file based everyplayThumbnailReadyAt(FilePath|URL): delegates

### Android v1.4.0 - June 29th 2015 (build 1400)

- Now allows 60fps recordings on Android 4.4+ devices

  To change the target framerate from the default 30fps,
  call Everyplay.setTargetFPS()

- Improved frame synchronization and framerate handling

- Fixed an audio issue with FMOD Studio that
  could have resulted to a silent recording

- Removed setThumbnailWidth method from Everyplay class

- Removed onEveryplayThumbnailReadyAtFilePath from IEveryplayListener

- Fixed an issue with PowerVR GPUs and continuous recording feature:
  If recording over 5 minutes while using setMaxRecordingMinutesLength,
  the device could freeze, fixed

## AIR 1970-1350 - Jun 3rd 2015

### iOS v1.9.7 - May 26th 2015 (build 1970)

- Metal: Graphics performance and memory usage optimizations

- Metal: Fixed a small memory leak that happened on every frame
  even while not recording

- Metal: Now supports HUD-less recording feature through
  [[[Everyplay sharedInstance] capture] snapshotRenderbuffer];

- Removed IDFA related code (AdSupport.framework), now uses IFV

- Removed EveryplaySoundEngine, OpenAL and AVFoundation implementations.
  Now uses Apple's high performance implementations when available

- Removed legacy OpenGL graphics integration API's from EveryplayCapture

- Removed support for file based thumbnails. If you use thumbnails,
  switch to texture based implementation

- Removed [Everyplay initWithDelegate:andAddRootViewControllerForView:]
  It was a helper for older world iOS apps that didn't implement
  UIViewController. Today, it's safe to assume that your code has them

- Increased the default video bitrate quality a bit

- Fixed a potential audio encoder memory leak while recording

### Android v1.3.5 - June 2nd 2015 (build 1350)

- New feature: Failsafe mode. If there's a crash during early
  initialization of Everyplay, the recording support will be
  disabled when the application is launched the next time

  Since the bug might be OS/driver related, the need for Failsafe
  mode is re-evaluated each time the SDK or OS has been upgraded
  or the application is removed

- Now supports Android M preview and fixes a crash against it.
  Older SDKs are disabled from recording against Android M

- More Qualcomm Adreno 420 crash fixes for some devices, like
  Samsung Galaxy Note 4

## AIR 1961-1332 - May 5th 2015

### iOS v1.9.6 - Apr 28th 2015 (build 1961)

- Metal: Fixed Facecam session handling when reseting
  session to audio only (1961)

## AIR 1960-1330 - Apr 29nd 2015

### Android v1.3.3 - Apr 28th 2015 (build 1330)

- Video quality improvement: On some devices and video codecs,
  the first second of the recording showed up as bit rotten,
  garbled output, fixed

- Fixed a graphics width vs stride regression from 1.3.0 SDK that
  could show up against the new graphics backend on some devices
  and driver versions, like Nexus 7 running Android 4.4

- On some rare devices, querying video codec info could cause
  application load times to slow down by 10 seconds, fixed

- Improved Everyplay.snapshotRenderbuffer() aka
  HUD-less recording feature

- Fix graphics issue with Samsung Galaxy S4 (PowerVR variant)

## AIR 1960-1320 - Apr 22nd 2015

### iOS v1.9.6 - Apr 16th 2015 (build 1960)

- Improved graphics support against Unity 5.x

- Metal: Fixed thumbnail texture being flipped

- Metal: Fixed to support dynamic screen resolution changes

- Fixed a regression against AVAudioPlayer initWithData: support

- Fixed a compatibility issue with InMobi SDK

### Android v1.3.2 - Apr 16th 2015 (build 1320)

- Improved graphics support against Unity 5.x

- Multiple stability fixes against ImgTec PowerVR GPU

- Improve OpenGL ES1 support checking

- Prefetching data could cause an exception, fixed

- Fixed a rare login exception on Android 4.0.x

- Minor audio handling improvements

## AIR 1950-1310 - Apr 10th 2015

### Android v1.3.1 - Mar 24th 2015 (build 1310)

- Fixed a regression with setMaxRecordingMinutesLength from not
  working against the new graphics backend on Android 4.3+

- Improved potential memory usage and buffer refcount
  issues for some GPU drivers

- Fixed potential exceptions for general login, sharing
  and Facebook related code

- Fixed video player view from not loading on Android 4.0.x

- Fixed exception with the photo picker

- AndroidManifest.xml tweak to allow Android TV support

## AIR 1950-1300 - Mar 12th 2015

### Android v1.3.0 - Mar 10th 2015 (build 1300)

- All-new graphics processing backend for Android 4.3+, improving
  framerate and stability a lot on many devices

- Greatly improved support for Nvidia GPUs (Tegra 3, Tegra 4, Tegra K1)

- Important AndroidManifest.xml changes to improve overall stability
  and reduce memory usage. If you're maintaining the manifest manually
  in your project, please merge the latest changes

- Fixes to potential crashes while using the login activity

- Fixed Javascript binding issues against some Android 4.4.x
  releases that prevented Everyplay Social views from working

- Fix potential performance issues when used against OpenGL ES3

- On some Android versions, changing to another Activity and returning
  could have prevented starting of a new recording from working, fixed

- Fixed a GPU driver caused ADB log flood issue; seen on some devices
  while recording

- Improved image quality on apps with 32-bit color graphics

- Multiple Nexus 10 specific issues fixed

- Now supports Nvidia Shield Portable, Nvidia Shield Tablet
  and Nexus 9 devices

## AIR 1950-1240 - Feb 23th 2015

### iOS v1.9.5 - Feb 20th 2015 (build 1950)

- iOS 8 Metal improvements: Now supports Live FaceCam preview box,
  thumbnail files/textures and using MTLPixelFormatRGBA8Unorm_sRGB

- Now supports OpenAL audio streaming through alSourceQueueBuffers

- Fix a conditition between showing modal share dialog and video editor
  that could lead to everyplayHidden delegate not properly called, potentially
  leading to game not being resumed as expected

- Fixed an issue with Cocos2d's scaled graphics on iPhone 6 Plus that prevented
  the recording from starting properly

- Facebook: Remove use of deprecated publish_stream permission

- Lighter UI theme

### Android v1.2.4 - Feb 20th 2015 (build 1240)

- More Android 5 Lollipop and Android Simulator fixes;
  null pointer exceptions, activity handling changes

- Fixed an issue with 64bit Android 5 devices that prevented
  looking up package name properly

- Querying device specific settings now wait until
  Everyplay.initEveryplay is called

- Facebook: Remove use of deprecated publish_stream permission

- Lighter UI theme

## AIR 1940-1230 - Feb 4th 2015

- Add support for iOS arm64 binary

## AIR 1940-1230 - Jan 15th 2015

### iOS v1.9.4 - Jan 14th 2015 (build 1940)

- Improved Facebook integration by asking server-side
  configuration status

- Improved AVFoundation/AVAudioPlayer usage against
  small sound effects

### Android v1.2.3 - Jan 14th 2015 (build 1230)

- Fix a null pointer exception that could cause a crash on some
  Android 5 Lollipop devices

- Fix a graphics performance issue with glDiscardFramebufferEXT
  that could affect some Android versions/drivers shipped

- Fix a CORS issue with Android 5 WebResourceResponse

- Improved Facebook integration by asking server-side
  configuration status

## AIR 1930-1220 - Dec 17th 2014

### iOS v1.9.3 - Dec 17th 2014 (build 1930)

- Fixed an issue with modal share dialog not appearing
  on some viewController configurations

### Android v1.2.2 - Dec 17th 2014 (build 1220)

- Fixed a rare ClassNotFoundException with Parcel unable to find
  com.everyplay.Everyplay.communication.EveryplayResultReceiver

## AIR 1921-1210 - Dec 11th 2014

### iOS v1.9.2 - Dec 10th 2014 (build 1921)

- [Everyplay initWithDelegate:] improvements

- [Everyplay sharedInstance].everyplayDelegate is now a weak pointer

- Minor UI and theming improvements

### Android v1.2.1 - Dec 10th 2014 (build 1210)

- App specific cached files now get removed upon
  application uninstallation

- Improved caching

- Minor UI and theming improvements

## AIR 1910-1200 - Dec 8th 2014

### iOS v1.9.1 - Nov 28th 2014 (build 1910)

- Network access and caching optimizations

- Video seek bar and video ending event fixes for
  the new video player

- [Everyplay sharedInstance].parentViewController is now a weak pointer

- Improved UI orientation handling

### Android v1.2 - Nov 28th 2014 (build 1200)

- Generic optimizations against the new Everyplay community

- New navigation top bar design to give more space while browsing

- Network access and caching optimizations

- Internal changes for UI theming support

- 3rdparty java code is relocated to another package namespace
  to avoid conflicts

- Performance updates to media merging and trimming

- Everyplay.setMaxRecordingMinutesLength didn't trim the
  resulting video, fixed

- Fixed potential crash issue with camera photo picker

- Upload performance improvements

- Everyplay.initEveryplay now retains IEveryplayListener

- Try-catch blocks for rare exceptions added

## AIR 1901-1160 - Nov 10th 2014

### iOS v1.9.0 - Nov 10th 2014 (build 1901)

- First iOS 8 Metal graphics support, no support for Live FaceCam
  preview box or thumbnail files/textures yet

- Video editor / player core and UI rewritten

- Everyplay.bundle graphics update, using fewer files and less space

- Internal changes for UI theming support

- Landscape support enabled by default for all iPhone views

- New navigation top bar design to give more space while browsing

- Improved memory handling

- Improved analytics

- Fixed thumbnail texture handling on iOS 8

- Improved FaceCam audio and video support and removed deprecated API
  usage warnings while running on iOS 7+

### Android v1.1.6 - Nov 10th 2014 (build 1160)

- Changes to activity handling in code and on AndroidManifest.xml
  to fix GPU driver issues and potential crashes

- Improved AAC encoded sound quality

- Improved Facebook behaviour for the future

## AIR 1840-1150 - Oct 9th 2014

- Add implementation for mergeSessionDeveloperData

### iOS v1.8.4 - Oct 9th 2014 (build 1840)

- Improved avatar photo picker and camera orientation handling

- Improved stereo support for AVFoundation / OpenAL

- OpenAL: Within game code, setting a negative value through
  alSourcef(x, AL_GAIN, volume) could cause iOS 8 mediaserverd to hang
  and cause multiple side effects until the device is rebooted, fixed

- everyplayFaceCamRecordingPermission delegate improvements

### Android v1.1.5 - Oct 9th 2014 (build 1150)

- Fixed Facebook sharing to work against Facebook API 2.0
  and later

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

  This behaviour is mostly seen on some custom engines and cocos2d

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
