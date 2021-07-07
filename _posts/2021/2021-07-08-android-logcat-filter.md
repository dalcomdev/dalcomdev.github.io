---
published: true
toc: true
categories:
  - Android
---

## Android logcat filter
> Logcat 에서 원하지 않는 System 로그나 기타 로그를 필터링 하는 방법  

### Logcat 필터
아래 필터를 복사하여 Log Tag 항목에 붙여 넣는다. 해당 항목은 필터링 되어 Logcat 에 나오지 않게 된다.
   
^(?!(WifiMulticast|WifiHW|MtpService|PushClient|InputMethodManager|Provider|SurfaceTextureClient|ImageLoader|dalvikvm|OpenGLRenderer|skia|AbsListView|MediaPlayer|AudioManager|VelocityTracker|Drv|Jpeg|CdpDrv|IspDrv|TpipeDrv|iio|ImgScaler|IMG_MMU|ResMgrDrv|JpgDecComp|JpgDecPipe|mHalJpgDec|PipeMgrDrv|mHalJpgParser|jdwp|libEGL|Zygote|Trace|InputEventReceiver|SpannableStringBuilder|IInputConnectionWrapper|MotionRecognitionManager|Choreographer|v_galz|SensorManager|Sensors|GC|LockPatternUtils|SignalStrength|STATUSBAR-BatteryController|BatteryService|STATUSBAR-PhoneStatusBar|WifiP2pStateTracker|Watchdog|AlarmManager|BatteryStatsImpl|STATUSBAR-Clock|SurfaceControl|ViewRootImpl|InputTransport))

### Package Name 항목
자신의 앱 패키지를 넣는다.

### 결론
Logcat 은 유용하지만 원하지 않는 로그가 너무 많이 나와서 이또한 시간이 걸리는 작업이 될 수 있다.  
적절한 필터를 넣음으로서 깔끔한 로그를 출력해 볼 수 있다.