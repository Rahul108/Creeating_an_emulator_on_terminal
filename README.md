# Creating Android Emulator on terminal

**Step 1:** 

Make sure Android SDK is configured properly. If not then download the leatest sdk tool file from [here](https://developer.android.com/studio#downloads). Ususally u can find it on `Command line tools only` section. 
```sh 
$ wget https://dl.google.com/android/repository/sdk-tools-linux-4333796.zip
```
Then run sdkmanager to see which images and tools are available
```sh
$ cd tools/bin/
$ ./sdkmanager --list
```
it will show all available images and tools, of which is on my pc and which are available to download, like this-
```sh
Installed packages:=====================] 100% Computing updates...             
  Path                                               | Version | Description                             | Location                                           
  -------                                            | ------- | -------                                 | -------                                            
  build-tools;28.0.3                                 | 28.0.3  | Android SDK Build-Tools 28.0.3          | build-tools/28.0.3/                                
  build-tools;29.0.0                                 | 29.0.0  | Android SDK Build-Tools 29              | build-tools/29.0.0/                                
  build-tools;29.0.1                                 | 29.0.1  | Android SDK Build-Tools 29.0.1          | build-tools/29.0.1/                                
  emulator                                           | 29.2.1  | Android Emulator                        | emulator/                                          
 ... ... ... ...
 ... ... ... ... 
  system-images;android-25;default;x86_64                                                  | 1            | Intel x86 Atom_64 System Image                                      
  system-images;android-25;google_apis;arm64-v8a                                           | 16           | Google APIs ARM 64 v8a System Image                                 
  system-images;android-25;google_apis;armeabi-v7a                                         | 16           | Google APIs ARM EABI v7a System Image                               
  system-images;android-25;google_apis;x86                                                 | 16           | Google APIs Intel x86 Atom System Image                             
  system-images;android-25;google_apis;x86_64                                              | 16           | Google APIs Intel x86 Atom_64 System Image                          
  system-images;android-25;google_apis_playstore;x86                                       | 9            | Google Play Intel                                                                                                  
  ```
  Make sure to install platforms, platform-tools, build-tools, emulator if these not exist
  
  For other functions of sdkmanager see
```sh
$ ./sdkmanager --help
Usage: 
  sdkmanager [--uninstall] [<common args>] [--package_file=<file>] [<packages>...]
  sdkmanager --update [<common args>]
  sdkmanager --list [<common args>]
  sdkmanager --licenses [<common args>]
  sdkmanager --version

With --install (optional), installs or updates packages.
    By default, the listed packages are installed or (if already installed)
    updated to the latest version.
With --uninstall, uninstall the listed packages.

    <package> is a sdk-style path (e.g. "build-tools;23.0.0" or
             "platforms;android-23").
    <package-file> is a text file where each line is a sdk-style path
                   of a package to install or uninstall.
    Multiple --package_file arguments may be specified in combination
    with explicit paths.

With --update, all installed packages are updated to the latest version.

With --list, all installed and available packages are printed out.

With --licenses, show and offer the option to accept licenses for all
     available packages that have not already been accepted.

With --version, prints the current version of sdkmanager.

Common Arguments:
    --sdk_root=<sdkRootPath>: Use the specified SDK root instead of the SDK 
                              containing this tool

    --channel=<channelId>: Include packages in channels up to <channelId>.
                           Common channels are:
                           0 (Stable), 1 (Beta), 2 (Dev), and 3 (Canary).

    --include_obsolete: With --list, show obsolete packages in the
                        package listing. With --update, update obsolete
                        packages as well as non-obsolete.

    --no_https: Force all connections to use http rather than https.

    --proxy=<http | socks>: Connect via a proxy of the given type.

    --proxy_host=<IP or DNS address>: IP or DNS address of the proxy to use.

    --proxy_port=<port #>: Proxy port to connect to.

    --verbose: Enable verbose output.

* If the env var REPO_OS_OVERRIDE is set to "windows",
  "macosx", or "linux", packages will be downloaded for that OS.
```
To download an image or a tool
```sh
$ ./sdkmanager "build-tools;29.0.2"
$ ./sdkmanager "platforms;android-28"
$ ./sdkmanager "build-tools;29.0.0 "
$ ./sdkmanager "emulator"
$ ./sdkmanager "platform-tools"
.........
etc
```
And at last, set path variable correctly on `.bashrc`

```sh
export ANDROID_AVD_HOME="$HOME/.android/avd"
export ANDROID_HOME="$HOME/Android/Sdk"
export PATH="$PATH:$ANDROID_HOME/tools"
export PATH="$PATH:$ANDROID_HOME/platform-tools"
export PATH="$PATH:$ANDROID_HOME/bundle-tool"
```

**Step 2:** 

Open avdmanager and see if its working or not.
```sh
cd ~/Android/Sdk/tools/bin/
```
See avdmanager mannuals, cause instruction code varies from version to version
```sh
$ ./avdmanager --help
Usage:
      avdmanager [global options] [action] [action options]
      Global options:
  -s --silent     : Silent mode, shows errors only.
  -v --verbose    : Verbose mode, shows errors, warnings and all messages.
     --clear-cache: Clear the SDK Manager repository manifest cache.
  -h --help       : Help on a specific command.

Valid actions are composed of a verb and an optional direct object:
-   list              : Lists existing targets or virtual devices.
-   list avd          : Lists existing Android Virtual Devices.
-   list target       : Lists existing targets.
-   list device       : Lists existing devices.
- create avd          : Creates a new Android Virtual Device.
-   move avd          : Moves or renames an Android Virtual Device.
- delete avd          : Deletes an Android Virtual Device.
```
We will create a virtual device using avdmanager, first see which devices are installed and which devices are available to download
```sh 
$ ./avdmanager list  
Parsing /home/rahul/Android/Sdk/build-tools/28.0.3/package.xmlParsing /home/rahul/Android/Sdk/build-tools/29.0.0/package.xmlParsing /home/rahul/Android/Sdk/build-tools/29.0.1/package.xmlParsing /home/rahul/Android/Sdk/emulator/package.xmlParsing /home/rahul/Android/Sdk/patcher/v4/package.xmlParsing /home/rahul/Android/Sdk/platform-tools/package.xmlParsing /home/rahul/Android/Sdk/platforms/android-23/package.xmlParsing /home/rahul/Android/Sdk/platforms/android-28/package.xmlParsing /home/rahul/Android/Sdk/platforms/android-29/package.xmlParsing /home/rahul/Android/Sdk/system-images/android-27/google_apis/x86/package.xmlParsing /home/rahul/Android/Sdk/system-images/android-28/google_apis/x86/package.xmlParsing /home/rahul/Android/Sdk/system-images/android-28/google_apis_playstore/x86/package.xmlParsing /home/rahul/Android/Sdk/system-images/android-29/google_apis/x86/package.xmlParsing /home/rahul/Android/Sdk/tools/package.xmlAvailable Android Virtual Devices:
    Name: Pixel_API_28
  Device: pixel (Google)
    Path: /home/rahul/.android/avd/Pixel_API_28.avd
  Target: Google Play (Google Inc.)
          Based on: Android API 28 Tag/ABI: google_apis_playstore/x86
    Skin: pixel_silver
  Sdcard: 512M

... ... ... ... ...
... ... ... ... ...

id: 1 or "android-23"
     Name: Android API 23
     Type: Platform
     API level: 23
     Revision: 3
----------
id: 2 or "android-28"
     Name: Android API 28
     Type: Platform
     API level: 28
     Revision: 6
----------
id: 3 or "android-29"
     Name: Android API 29
     Type: Platform
     API level: 29
     Revision: 3
```
To create a custom virtual device-
```sh
$ ./avdmanager create avd -n MyEmulator -k "system-images;android-28;google_apis;x86" -d 19
```

In order to work on root device, choose sdk naming like 
```sh
Google APIs Intel x86 Atom System Image
```
not
```sh
Google Play Intel x86 Atom System Image
```
Here:

* -n is my emulator name =  MyEmulator
* -k is the downloaded image version with sdkmanager. Through `./sdkmanager --list`, it is found on `Installed Packages` section! Also u can use an image from `Availabe Packages` section, but on that case, it will first download the image and then create the virtual device.
* -d is the device id, can be found with `./avdmanager --list`, specifies on which device i want to install the image..

**Step 3:** To see the virtual device has created or not , there are some ways..

One way is to use avdmanager
```sh
$ cd ~/Android/Sdk/tools/bin/
$ ./avdmanager --list
```
a section named `Availabe Android Virtual Devices` appears on result on which the installed devices can be seen like this-
```sh
....................
Available Android Virtual Devices:
    Name: MyEmulator
  Device: pixel_xl (Google)
    Path: /home/rahul/.android/avd/MyEmulator.avd
  Target: Google APIs (Google Inc.)
          Based on: Android API 28 Tag/ABI: google_apis/x86
---------
    Name: Pixel_API_28
  Device: pixel (Google)
    Path: /home/rahul/.android/avd/Pixel_API_28.avd
  Target: Google Play (Google Inc.)
          Based on: Android API 28 Tag/ABI: google_apis_playstore/x86
    Skin: pixel_silver
  Sdcard: 512M
.....................
```

Other way is to use `emulator`. It will show the name of all the available virtual devices installed currenty.
```sh
$ cd ~/Android/Sdk/emulator/
$ ./emulator -list-avds
MyEmulator
Pixel_API_28
```

**Step 4:** 

To run the emulator type the emulator name that i gave while creating it. On my case its `MyEmulator`
```sh
$ cd ~/Android/Sdk/emulator/
$ ./emulator -avd MyEmulator 
```
