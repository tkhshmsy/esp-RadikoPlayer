# esp-RadikoPlayer

to execute the sample-code of [WebRadio_Japan](https://github.com/wakwak-koba/WebRadio_Japan).

## Requirement

for building with PlatformIO

* H/W
  * M5StickC
    * It's old product, so here is M5StickC-PLUS.
    * https://shop.m5stack.com/collections/m5-controllers/products/m5stickc-plus-esp32-pico-mini-iot-development-kit
  * SPK HAT
    * https://shop.m5stack.com/products/m5stickc-speaker-hat
* Libraries
  * m5stack/M5Unified@^0.1.1
  * https://github.com/pschatzmann/arduino-libhelix
  * https://github.com/wakwak-koba/ESP8266Audio
  * https://github.com/wakwak-koba/WebRadio_Japan
* Auth
  * [Radiko](https://radiko.jp/) ID/PW
    * 'free account' is valid to use.
* HostPC
  * Ubuntu 22.04 LTS
  * PlatformIO 6.1.5

## Patch ESP8266Audio

it needs to patch for wakwak-koba/ESP8266Audio.

base is https://github.com/wakwak-koba/ESP8266Audio/commit/94d8b645cffb57b97885138390a35e3f6c89a394

```diff
diff --git a/src/AudioGeneratorAAC.cpp b/src/AudioGeneratorAAC.cpp
index 7910757..503a4e8 100644
--- a/src/AudioGeneratorAAC.cpp
+++ b/src/AudioGeneratorAAC.cpp
@@ -21,7 +21,7 @@
 #pragma GCC optimize ("O3")
 
 #include "AudioGeneratorAAC.h"
-#include "libhelix-aac\aaccommon.h"
+#include "libhelix-aac/aaccommon.h"
 #include "allocate-memory.h"
 
 AudioGeneratorAAC::AudioGeneratorAAC(bool enableSBR)
```
