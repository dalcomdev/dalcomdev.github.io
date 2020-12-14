---
published: false
---
---
toc: true
categories:
  - Android
tags:
  - android
---

## Android storage 구조
Android 에서는 흔히 sdcard 라고 말하면 removable 메모리 카드를 말하는 경우가 있는데, 개념적으로는 구분되어 있지 않다.  
간단하게는 아래와 같이 이야기 할 수 있다.

| 구분 | 설명 |
|--|--|
| internal | 앱에서 사용하는 저장공간.  Permission 획득없이, File 객체로 접근가능하다.|
| external | 공용 저장공간.  Read/Write 하기 위해서는 Permission 획득이 필요하다. |

- 저장소 경로 예제
  - internal: /data/data/com.my.app/
  - external: /sdcard/Download

## Android 11 이상 target 단말에서 external sd card 확인하는 방법
---

Android 11 이전 단말에서는 sd memory card 를 확인하는 방법이 복잡하다.  
여러가지 체크해야할 포인트도 많고, 단말마다 다른결과가 나오기도 한다. 
아래와 비슷한 코드들을 사용하게 되는데, Android 11 이상 단말에서 코드를 그대로 사용하여, File 클래스의 __listFiles()__ 를 호출하면 모든파일접근 권한을 가지고 있지 않는한, [Android 11 scoped storage](https://developer.android.com/training/data-storage?#scoped-storage) 제약사항 때문에 exception 을 만나게 된다.

```java
...
final File externalStorageRoot = new File( externalStorageRootDir );
final File[] files = externalStorageRoot.listFiles();

for ( final File file : files ) {
  if ( file.isDirectory() && file.canRead() && (file.listFiles().length > 0) ) {  // it is a real directory (not a USB drive)...
    Log.d(TAG, "External Storage: " + file.getAbsolutePath() + "\n");
  }
}
...
```

## Android 11 이상에서는 StorageManager 사용
---

Android 11 부터는 StorageManager 를 사용하여 구현 하면 된다.

```java
@RequiresApi(api = Build.VERSION_CODES.R)
private boolean isExternalSdcardAvailable() {
  File[] extDirs = getContext().getExternalFilesDirs(null);
  boolean isAvailable = false;

  for (File file : extDirs) {
    StorageVolume storageVolume = mStorageManager.getStorageVolume(file);
    if (storageVolume != null
        && !storageVolume.isPrimary()
        && storageVolume.isRemovable()) {

      long totalSpace = file.getTotalSpace();
      long freeSpace = file.getFreeSpace();

      if (freeSpace > 0) {
        isAvailable = true;
        break;
      }
    }
  }
  return isAvailable;
}
```

이상 Android 11 이상에서 external sd card 확인하는 방법이다.



