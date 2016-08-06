This project is copied from lorenzogomez/RERAN and makes several changes due to the update of platform-tools.

step 1:
  arm-none-linux-gnueabi-gcc -static -o replay replay.c
step 2:
  adb push replay /sdcard/
 adb shell su -c cp /sdcard/replay /data/local/

step 3:
  adb shell getevent -tt > recordedEvents.txt

step 4:
  Translate recordedEvents.txt out.txt

step 5:
   adb push out.txt /sdcard/
  adb shell su -c cp /sdcard/out.txt /data/local/

step 6: 
  adb shell
  su
  cd /data/local
  ./replay out.txt


If you want to generate human readable recordedEvents.txt use:
 adb shell getevent -tl > recordedEvents.txt
