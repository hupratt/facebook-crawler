# Facebook crawler for bulk picture download

## Stack: 

1. Waydroid for android emulation. Waydroid is a LXE container (not the same as a docker container). Linux should have the display setting set to Wayland (Not X11) in order for Waydroid to work
2. Apium inspector to make it easier to find HTML tags. Having worked with Selenium scripting for years I can tell you this makes all the difference. It's open source too check it out. There's even a record option that works like macro recordings in excel
3. Appium server acts as a JSON layer between Selenium and the Apium inspector 
4. Python the agent that orchestrates the web browsing downloading pictures
5. Java
6. Android SDK, we'll use adb exclusively so you don't need android studio
7. [The Waydroid extension from casualsnek](https://github.com/casualsnek/waydroid_script). He has a guide on how to get the google play store on Waydroid which is useful to install the firefox APK that we'll use to scrape facebook

## Linux commands:

1st shell

`virtualenv env`

`source env/bin/activate`

`pip install -r requirements.txt`

`python appiumscript.py`

2nd shell

`export JAVA_HOME=/your/path/openjdk11`

`export ANDROID_HOME=/your/path/AndroidSDK`

`adb connect <waydroid IP>:5555`

`appium -p 9000 -a 127.0.0.1 --allow-cors`

## Video of the script working:
[![Watch the video](Waydroid.jpg)](waydroid_resized.avi)