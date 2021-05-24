# Enabling Signature Spoofing in Android 11
### First I want to thank Lanchon without whom none of this would have been possible. 
So, you want microG on Lineage 18.1. But wait, NanoDroid Patcher doesnt work! So what do you do? well obviously, you search on Google and find nothing except a badly written XDA Post.
I am here to help! I am just rewriting that post in a better format.

[Source](https://forum.xda-developers.com/t/signature-spoofing-on-unsuported-android-11-r-roms.4214143/)

### A linux machine (NOT WSL) is preferable here. I will be using bash here.

- Enable ROOT-ADB-Debugging
  1. Enable Developer Settings by tapping Build Number 7 times
  2. Enable USB Debugging and ADB Root

- Patch services.jar
  1. Git Clone this Repo.
  2. Install ADB Drivers.
  3. Unzip haystack.zip and add dexpatcher.jar inside it. 
  4. Do ```adb pull /system/framework/services.jar```. This pulls the services.jar of your phone.
  5. Do ```java -jar dexpatcher-1.8.0-beta1.jar -a 11 -M -v -d -o ./ services.jar 11-hook-services.jar.dex 11core-services.jar.dex```. Yes. You need to do it from terminal/commandline. No GUI is availiable
  6. Do ```mkdir repack``` or make a folder named repack
  7. Do ``````
