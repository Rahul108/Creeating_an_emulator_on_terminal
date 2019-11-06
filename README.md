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
  patcher;v4                                         | 1       | SDK Patch Applier v4                    | patcher/v4/                                        
  platform-tools                                     | 29.0.5  | Android SDK Platform-Tools              | platform-tools/                                    
  platforms;android-23                               | 3       | Android SDK Platform 23                 | platforms/android-23/                              
  platforms;android-28                               | 6       | Android SDK Platform 28                 | platforms/android-28/                              
  platforms;android-29                               | 3       | Android SDK Platform 29                 | platforms/android-29/                              
  system-images;android-27;google_apis;x86           | 9       | Google APIs Intel x86 Atom System Image | system-images/android-27/google_apis/x86/          
  system-images;android-28;google_apis;x86           | 9       | Google APIs Intel x86 Atom System Image | system-images/android-28/google_apis/x86/          
  system-images;android-28;google_apis_playstore;x86 | 8       | Google Play Intel x86 Atom System Image | system-images/android-28/google_apis_playstore/x86/
  system-images;android-29;google_apis;x86           | 8       | Google APIs Intel x86 Atom System Image | system-images/android-29/google_apis/x86/          
  tools                                              | 26.1.1  | Android SDK Tools                       | tools/                                             

Available Packages:
  Path                                                                                     | Version      | Description                                                         
  -------                                                                                  | -------      | -------                                                             
  add-ons;addon-google_apis-google-15                                                      | 3            | Google APIs                                                         
  add-ons;addon-google_apis-google-16                                                      | 4            | Google APIs                                                         
  add-ons;addon-google_apis-google-17                                                      | 4            | Google APIs                                                         
  add-ons;addon-google_apis-google-18                                                      | 4            | Google APIs                                                         
  add-ons;addon-google_apis-google-19                                                      | 20           | Google APIs                                                         
  add-ons;addon-google_apis-google-21                                                      | 1            | Google APIs                                                         
  add-ons;addon-google_apis-google-22                                                      | 1            | Google APIs                                                         
  add-ons;addon-google_apis-google-23                                                      | 1            | Google APIs                                                         
  add-ons;addon-google_apis-google-24                                                      | 1            | Google APIs                                                         
  add-ons;addon-google_gdk-google-19                                                       | 11           | Glass Development Kit Preview                                       
  build-tools;19.1.0                                                                       | 19.1.0       | Android SDK Build-Tools 19.1                                        
  build-tools;20.0.0                                                                       | 20.0.0       | Android SDK Build-Tools 20                                          
  build-tools;21.1.2                                                                       | 21.1.2       | Android SDK Build-Tools 21.1.2                                      
  build-tools;22.0.1                                                                       | 22.0.1       | Android SDK Build-Tools 22.0.1                                      
  build-tools;23.0.1                                                                       | 23.0.1       | Android SDK Build-Tools 23.0.1                                      
  build-tools;23.0.2                                                                       | 23.0.2       | Android SDK Build-Tools 23.0.2                                      
  build-tools;23.0.3                                                                       | 23.0.3       | Android SDK Build-Tools 23.0.3                                      
  build-tools;24.0.0                                                                       | 24.0.0       | Android SDK Build-Tools 24                                          
  build-tools;24.0.1                                                                       | 24.0.1       | Android SDK Build-Tools 24.0.1                                      
  build-tools;24.0.2                                                                       | 24.0.2       | Android SDK Build-Tools 24.0.2                                      
  build-tools;24.0.3                                                                       | 24.0.3       | Android SDK Build-Tools 24.0.3                                      
  build-tools;25.0.0                                                                       | 25.0.0       | Android SDK Build-Tools 25                                          
  build-tools;25.0.1                                                                       | 25.0.1       | Android SDK Build-Tools 25.0.1                                      
  build-tools;25.0.2                                                                       | 25.0.2       | Android SDK Build-Tools 25.0.2                                      
  build-tools;25.0.3                                                                       | 25.0.3       | Android SDK Build-Tools 25.0.3                                      
  build-tools;26.0.0                                                                       | 26.0.0       | Android SDK Build-Tools 26                                          
  build-tools;26.0.1                                                                       | 26.0.1       | Android SDK Build-Tools 26.0.1                                      
  build-tools;26.0.2                                                                       | 26.0.2       | Android SDK Build-Tools 26.0.2                                      
  build-tools;26.0.3                                                                       | 26.0.3       | Android SDK Build-Tools 26.0.3                                      
  build-tools;27.0.0                                                                       | 27.0.0       | Android SDK Build-Tools 27                                          
  build-tools;27.0.1                                                                       | 27.0.1       | Android SDK Build-Tools 27.0.1                                      
  build-tools;27.0.2                                                                       | 27.0.2       | Android SDK Build-Tools 27.0.2                                      
  build-tools;27.0.3                                                                       | 27.0.3       | Android SDK Build-Tools 27.0.3                                      
  build-tools;28.0.0                                                                       | 28.0.0       | Android SDK Build-Tools 28                                          
  build-tools;28.0.1                                                                       | 28.0.1       | Android SDK Build-Tools 28.0.1                                      
  build-tools;28.0.2                                                                       | 28.0.2       | Android SDK Build-Tools 28.0.2                                      
  build-tools;28.0.3                                                                       | 28.0.3       | Android SDK Build-Tools 28.0.3                                      
  build-tools;29.0.0                                                                       | 29.0.0       | Android SDK Build-Tools 29                                          
  build-tools;29.0.1                                                                       | 29.0.1       | Android SDK Build-Tools 29.0.1                                      
  build-tools;29.0.2                                                                       | 29.0.2       | Android SDK Build-Tools 29.0.2                                      
  cmake;3.10.2.4988404                                                                     | 3.10.2       | CMake 3.10.2.4988404                                                
  cmake;3.6.4111459                                                                        | 3.6.4111459  | CMake 3.6.4111459                                                   
  docs                                                                                     | 1            | Documentation for Android SDK                                       
  emulator                                                                                 | 29.2.1       | Android Emulator                                                    
  extras;android;gapid;1                                                                   | 1.0.3        | GPU Debugging tools                                                 
  extras;android;gapid;3                                                                   | 3.1.0        | GPU Debugging tools                                                 
  extras;android;m2repository                                                              | 47.0.0       | Android Support Repository                                          
  extras;google;auto                                                                       | 1.1          | Android Auto Desktop Head Unit emulator                             
  extras;google;google_play_services                                                       | 49           | Google Play services                                                
  extras;google;instantapps                                                                | 1.9.0        | Google Play Instant Development SDK                                 
  extras;google;m2repository                                                               | 58           | Google Repository                                                   
  extras;google;market_apk_expansion                                                       | 1            | Google Play APK Expansion library                                   
  extras;google;market_licensing                                                           | 1            | Google Play Licensing Library                                       
  extras;google;simulators                                                                 | 1            | Android Auto API Simulators                                         
  extras;google;webdriver                                                                  | 2            | Google Web Driver                                                   
  extras;m2repository;com;android;support;constraint;constraint-layout-solver;1.0.0        | 1            | Solver for ConstraintLayout 1.0.0                                   
  extras;m2repository;com;android;support;constraint;constraint-layout-solver;1.0.0-alpha4 | 1            | com.android.support.constraint:constraint-layout-solver:1.0.0-alpha4
  extras;m2repository;com;android;support;constraint;constraint-layout-solver;1.0.0-alpha8 | 1            | Solver for ConstraintLayout 1.0.0-alpha8                            
  extras;m2repository;com;android;support;constraint;constraint-layout-solver;1.0.0-beta1  | 1            | Solver for ConstraintLayout 1.0.0-beta1                             
  extras;m2repository;com;android;support;constraint;constraint-layout-solver;1.0.0-beta2  | 1            | Solver for ConstraintLayout 1.0.0-beta2                             
  extras;m2repository;com;android;support;constraint;constraint-layout-solver;1.0.0-beta3  | 1            | Solver for ConstraintLayout 1.0.0-beta3                             
  extras;m2repository;com;android;support;constraint;constraint-layout-solver;1.0.0-beta4  | 1            | Solver for ConstraintLayout 1.0.0-beta4                             
  extras;m2repository;com;android;support;constraint;constraint-layout-solver;1.0.0-beta5  | 1            | Solver for ConstraintLayout 1.0.0-beta5                             
  extras;m2repository;com;android;support;constraint;constraint-layout-solver;1.0.1        | 1            | Solver for ConstraintLayout 1.0.1                                   
  extras;m2repository;com;android;support;constraint;constraint-layout-solver;1.0.2        | 1            | Solver for ConstraintLayout 1.0.2                                   
  extras;m2repository;com;android;support;constraint;constraint-layout;1.0.0               | 1            | ConstraintLayout for Android 1.0.0                                  
  extras;m2repository;com;android;support;constraint;constraint-layout;1.0.0-alpha4        | 1            | com.android.support.constraint:constraint-layout:1.0.0-alpha4       
  extras;m2repository;com;android;support;constraint;constraint-layout;1.0.0-alpha8        | 1            | ConstraintLayout for Android 1.0.0-alpha8                           
  extras;m2repository;com;android;support;constraint;constraint-layout;1.0.0-beta1         | 1            | ConstraintLayout for Android 1.0.0-beta1                            
  extras;m2repository;com;android;support;constraint;constraint-layout;1.0.0-beta2         | 1            | ConstraintLayout for Android 1.0.0-beta2                            
  extras;m2repository;com;android;support;constraint;constraint-layout;1.0.0-beta3         | 1            | ConstraintLayout for Android 1.0.0-beta3                            
  extras;m2repository;com;android;support;constraint;constraint-layout;1.0.0-beta4         | 1            | ConstraintLayout for Android 1.0.0-beta4                            
  extras;m2repository;com;android;support;constraint;constraint-layout;1.0.0-beta5         | 1            | ConstraintLayout for Android 1.0.0-beta5                            
  extras;m2repository;com;android;support;constraint;constraint-layout;1.0.1               | 1            | ConstraintLayout for Android 1.0.1                                  
  extras;m2repository;com;android;support;constraint;constraint-layout;1.0.2               | 1            | ConstraintLayout for Android 1.0.2                                  
  lldb;2.0                                                                                 | 2.0.2558144  | LLDB 2.0                                                            
  lldb;2.1                                                                                 | 2.1.2852477  | LLDB 2.1                                                            
  lldb;2.2                                                                                 | 2.2.3271982  | LLDB 2.2                                                            
  lldb;2.3                                                                                 | 2.3.3614996  | LLDB 2.3                                                            
  lldb;3.0                                                                                 | 3.0.4213617  | LLDB 3.0                                                            
  lldb;3.1                                                                                 | 3.1.4508709  | LLDB 3.1                                                            
  ndk-bundle                                                                               | 20.0.5594570 | NDK                                                                 
  ndk;16.1.4479499                                                                         | 16.1.4479499 | NDK (Side by side) 16.1.4479499                                     
  ndk;17.2.4988734                                                                         | 17.2.4988734 | NDK (Side by side) 17.2.4988734                                     
  ndk;18.1.5063045                                                                         | 18.1.5063045 | NDK (Side by side) 18.1.5063045                                     
  ndk;19.2.5345600                                                                         | 19.2.5345600 | NDK (Side by side) 19.2.5345600                                     
  ndk;20.0.5594570                                                                         | 20.0.5594570 | NDK (Side by side) 20.0.5594570                                     
  patcher;v4                                                                               | 1            | SDK Patch Applier v4                                                
  platform-tools                                                                           | 29.0.5       | Android SDK Platform-Tools                                          
  platforms;android-10                                                                     | 2            | Android SDK Platform 10                                             
  platforms;android-11                                                                     | 2            | Android SDK Platform 11                                             
  platforms;android-12                                                                     | 3            | Android SDK Platform 12                                             
  platforms;android-13                                                                     | 1            | Android SDK Platform 13                                             
  platforms;android-14                                                                     | 4            | Android SDK Platform 14                                             
  platforms;android-15                                                                     | 5            | Android SDK Platform 15                                             
  platforms;android-16                                                                     | 5            | Android SDK Platform 16                                             
  platforms;android-17                                                                     | 3            | Android SDK Platform 17                                             
  platforms;android-18                                                                     | 3            | Android SDK Platform 18                                             
  platforms;android-19                                                                     | 4            | Android SDK Platform 19                                             
  platforms;android-20                                                                     | 2            | Android SDK Platform 20                                             
  platforms;android-21                                                                     | 2            | Android SDK Platform 21                                             
  platforms;android-22                                                                     | 2            | Android SDK Platform 22                                             
  platforms;android-23                                                                     | 3            | Android SDK Platform 23                                             
  platforms;android-24                                                                     | 2            | Android SDK Platform 24                                             
  platforms;android-25                                                                     | 3            | Android SDK Platform 25                                             
  platforms;android-26                                                                     | 2            | Android SDK Platform 26                                             
  platforms;android-27                                                                     | 3            | Android SDK Platform 27                                             
  platforms;android-28                                                                     | 6            | Android SDK Platform 28                                             
  platforms;android-29                                                                     | 3            | Android SDK Platform 29                                             
  platforms;android-7                                                                      | 3            | Android SDK Platform 7                                              
  platforms;android-8                                                                      | 3            | Android SDK Platform 8                                              
  platforms;android-9                                                                      | 2            | Android SDK Platform 9                                              
  sources;android-15                                                                       | 2            | Sources for Android 15                                              
  sources;android-16                                                                       | 2            | Sources for Android 16                                              
  sources;android-17                                                                       | 1            | Sources for Android 17                                              
  sources;android-18                                                                       | 1            | Sources for Android 18                                              
  sources;android-19                                                                       | 2            | Sources for Android 19                                              
  sources;android-20                                                                       | 1            | Sources for Android 20                                              
  sources;android-21                                                                       | 1            | Sources for Android 21                                              
  sources;android-22                                                                       | 1            | Sources for Android 22                                              
  sources;android-23                                                                       | 1            | Sources for Android 23                                              
  sources;android-24                                                                       | 1            | Sources for Android 24                                              
  sources;android-25                                                                       | 1            | Sources for Android 25                                              
  sources;android-26                                                                       | 1            | Sources for Android 26                                              
  sources;android-27                                                                       | 1            | Sources for Android 27                                              
  sources;android-28                                                                       | 1            | Sources for Android 28                                              
  sources;android-29                                                                       | 1            | Sources for Android 29                                              
  system-images;android-10;default;armeabi-v7a                                             | 5            | ARM EABI v7a System Image                                           
  system-images;android-10;default;x86                                                     | 5            | Intel x86 Atom System Image                                         
  system-images;android-10;google_apis;armeabi-v7a                                         | 6            | Google APIs ARM EABI v7a System Image                               
  system-images;android-10;google_apis;x86                                                 | 6            | Google APIs Intel x86 Atom System Image                             
  system-images;android-14;default;armeabi-v7a                                             | 2            | ARM EABI v7a System Image                                           
  system-images;android-15;default;armeabi-v7a                                             | 5            | ARM EABI v7a System Image                                           
  system-images;android-15;default;x86                                                     | 5            | Intel x86 Atom System Image                                         
  system-images;android-15;google_apis;armeabi-v7a                                         | 6            | Google APIs ARM EABI v7a System Image                               
  system-images;android-15;google_apis;x86                                                 | 6            | Google APIs Intel x86 Atom System Image                             
  system-images;android-16;default;armeabi-v7a                                             | 6            | ARM EABI v7a System Image                                           
  system-images;android-16;default;mips                                                    | 1            | MIPS System Image                                                   
  system-images;android-16;default;x86                                                     | 6            | Intel x86 Atom System Image                                         
  system-images;android-16;google_apis;armeabi-v7a                                         | 6            | Google APIs ARM EABI v7a System Image                               
  system-images;android-16;google_apis;x86                                                 | 6            | Google APIs Intel x86 Atom System Image                             
  system-images;android-17;default;armeabi-v7a                                             | 6            | ARM EABI v7a System Image                                           
  system-images;android-17;default;mips                                                    | 1            | MIPS System Image                                                   
  system-images;android-17;default;x86                                                     | 4            | Intel x86 Atom System Image                                         
  system-images;android-17;google_apis;armeabi-v7a                                         | 6            | Google APIs ARM EABI v7a System Image                               
  system-images;android-17;google_apis;x86                                                 | 6            | Google APIs Intel x86 Atom System Image                             
  system-images;android-18;default;armeabi-v7a                                             | 5            | ARM EABI v7a System Image                                           
  system-images;android-18;default;x86                                                     | 4            | Intel x86 Atom System Image                                         
  system-images;android-18;google_apis;armeabi-v7a                                         | 6            | Google APIs ARM EABI v7a System Image                               
  system-images;android-18;google_apis;x86                                                 | 6            | Google APIs Intel x86 Atom System Image                             
  system-images;android-19;default;armeabi-v7a                                             | 5            | ARM EABI v7a System Image                                           
  system-images;android-19;default;x86                                                     | 6            | Intel x86 Atom System Image                                         
  system-images;android-19;google_apis;armeabi-v7a                                         | 38           | Google APIs ARM EABI v7a System Image                               
  system-images;android-19;google_apis;x86                                                 | 38           | Google APIs Intel x86 Atom System Image                             
  system-images;android-21;android-tv;armeabi-v7a                                          | 3            | Android TV ARM EABI v7a System Image                                
  system-images;android-21;android-tv;x86                                                  | 3            | Android TV Intel x86 Atom System Image                              
  system-images;android-21;default;armeabi-v7a                                             | 4            | ARM EABI v7a System Image                                           
  system-images;android-21;default;x86                                                     | 5            | Intel x86 Atom System Image                                         
  system-images;android-21;default;x86_64                                                  | 5            | Intel x86 Atom_64 System Image                                      
  system-images;android-21;google_apis;armeabi-v7a                                         | 30           | Google APIs ARM EABI v7a System Image                               
  system-images;android-21;google_apis;x86                                                 | 30           | Google APIs Intel x86 Atom System Image                             
  system-images;android-21;google_apis;x86_64                                              | 30           | Google APIs Intel x86 Atom_64 System Image                          
  system-images;android-22;android-tv;x86                                                  | 3            | Android TV Intel x86 Atom System Image                              
  system-images;android-22;default;armeabi-v7a                                             | 2            | ARM EABI v7a System Image                                           
  system-images;android-22;default;x86                                                     | 6            | Intel x86 Atom System Image                                         
  system-images;android-22;default;x86_64                                                  | 6            | Intel x86 Atom_64 System Image                                      
  system-images;android-22;google_apis;armeabi-v7a                                         | 24           | Google APIs ARM EABI v7a System Image                               
  system-images;android-22;google_apis;x86                                                 | 24           | Google APIs Intel x86 Atom System Image                             
  system-images;android-22;google_apis;x86_64                                              | 24           | Google APIs Intel x86 Atom_64 System Image                          
  system-images;android-23;android-tv;armeabi-v7a                                          | 12           | Android TV ARM EABI v7a System Image                                
  system-images;android-23;android-tv;x86                                                  | 19           | Android TV Intel x86 Atom System Image                              
  system-images;android-23;android-wear;armeabi-v7a                                        | 6            | Android Wear ARM EABI v7a System Image                              
  system-images;android-23;android-wear;x86                                                | 6            | Android Wear Intel x86 Atom System Image                            
  system-images;android-23;default;armeabi-v7a                                             | 6            | ARM EABI v7a System Image                                           
  system-images;android-23;default;x86                                                     | 10           | Intel x86 Atom System Image                                         
  system-images;android-23;default;x86_64                                                  | 10           | Intel x86 Atom_64 System Image                                      
  system-images;android-23;google_apis;armeabi-v7a                                         | 31           | Google APIs ARM EABI v7a System Image                               
  system-images;android-23;google_apis;x86                                                 | 31           | Google APIs Intel x86 Atom System Image                             
  system-images;android-23;google_apis;x86_64                                              | 31           | Google APIs Intel x86 Atom_64 System Image                          
  system-images;android-24;android-tv;x86                                                  | 20           | Android TV Intel x86 Atom System Image                              
  system-images;android-24;default;arm64-v8a                                               | 7            | ARM 64 v8a System Image                                             
  system-images;android-24;default;armeabi-v7a                                             | 7            | ARM EABI v7a System Image                                           
  system-images;android-24;default;x86                                                     | 8            | Intel x86 Atom System Image                                         
  system-images;android-24;default;x86_64                                                  | 8            | Intel x86 Atom_64 System Image                                      
  system-images;android-24;google_apis;arm64-v8a                                           | 25           | Google APIs ARM 64 v8a System Image                                 
  system-images;android-24;google_apis;armeabi-v7a                                         | 25           | Google APIs ARM EABI v7a System Image                               
  system-images;android-24;google_apis;x86                                                 | 25           | Google APIs Intel x86 Atom System Image                             
  system-images;android-24;google_apis;x86_64                                              | 25           | Google APIs Intel x86 Atom_64 System Image                          
  system-images;android-24;google_apis_playstore;x86                                       | 19           | Google Play Intel x86 Atom System Image                             
  system-images;android-25;android-tv;x86                                                  | 14           | Android TV Intel x86 Atom System Image                              
  system-images;android-25;android-wear-cn;armeabi-v7a                                     | 4            | China version of Android Wear ARM EABI v7a System Image             
  system-images;android-25;android-wear-cn;x86                                             | 4            | China version of Android Wear Intel x86 Atom System Image           
  system-images;android-25;android-wear;armeabi-v7a                                        | 3            | Android Wear ARM EABI v7a System Image                              
  system-images;android-25;android-wear;x86                                                | 3            | Android Wear Intel x86 Atom System Image                            
  system-images;android-25;default;x86                                                     | 1            | Intel x86 Atom System Image                                         
  system-images;android-25;default;x86_64                                                  | 1            | Intel x86 Atom_64 System Image                                      
  system-images;android-25;google_apis;arm64-v8a                                           | 16           | Google APIs ARM 64 v8a System Image                                 
  system-images;android-25;google_apis;armeabi-v7a                                         | 16           | Google APIs ARM EABI v7a System Image                               
  system-images;android-25;google_apis;x86                                                 | 16           | Google APIs Intel x86 Atom System Image                             
  system-images;android-25;google_apis;x86_64                                              | 16           | Google APIs Intel x86 Atom_64 System Image                          
  system-images;android-25;google_apis_playstore;x86                                       | 9            | Google Play Intel x86 Atom System Image                             
  system-images;android-26;android-tv;x86                                                  | 12           | Android TV Intel x86 Atom System Image                              
  system-images;android-26;android-wear-cn;x86                                             | 4            | China version of Android Wear Intel x86 Atom System Image           
  system-images;android-26;android-wear;x86                                                | 4            | Android Wear Intel x86 Atom System Image                            
  system-images;android-26;default;x86                                                     | 1            | Intel x86 Atom System Image                                         
  system-images;android-26;default;x86_64                                                  | 1            | Intel x86 Atom_64 System Image                                      
  system-images;android-26;google_apis;x86                                                 | 14           | Google APIs Intel x86 Atom System Image                             
  system-images;android-26;google_apis;x86_64                                              | 14           | Google APIs Intel x86 Atom_64 System Image                          
  system-images;android-26;google_apis_playstore;x86                                       | 7            | Google Play Intel x86 Atom System Image                             
  system-images;android-27;android-tv;x86                                                  | 7            | Android TV Intel x86 Atom System Image                              
  system-images;android-27;default;x86                                                     | 1            | Intel x86 Atom System Image                                         
  system-images;android-27;default;x86_64                                                  | 1            | Intel x86 Atom_64 System Image                                      
  system-images;android-27;google_apis;x86                                                 | 9            | Google APIs Intel x86 Atom System Image                             
  system-images;android-27;google_apis_playstore;x86                                       | 3            | Google Play Intel x86 Atom System Image                             
  system-images;android-28;android-tv;x86                                                  | 8            | Android TV Intel x86 Atom System Image                              
  system-images;android-28;android-wear-cn;x86                                             | 3            | China version of Wear OS Intel x86 Atom System Image                
  system-images;android-28;android-wear;x86                                                | 3            | Wear OS Intel x86 Atom System Image                                 
  system-images;android-28;default;x86                                                     | 4            | Intel x86 Atom System Image                                         
  system-images;android-28;default;x86_64                                                  | 4            | Intel x86 Atom_64 System Image                                      
  system-images;android-28;google_apis;x86                                                 | 9            | Google APIs Intel x86 Atom System Image                             
  system-images;android-28;google_apis;x86_64                                              | 9            | Google APIs Intel x86 Atom_64 System Image                          
  system-images;android-28;google_apis_playstore;x86                                       | 8            | Google Play Intel x86 Atom System Image                             
  system-images;android-28;google_apis_playstore;x86_64                                    | 8            | Google Play Intel x86 Atom_64 System Image                          
  system-images;android-29;default;x86                                                     | 7            | Intel x86 Atom System Image                                         
  system-images;android-29;default;x86_64                                                  | 7            | Intel x86 Atom_64 System Image                                      
  system-images;android-29;google_apis;x86                                                 | 8            | Google APIs Intel x86 Atom System Image                             
  system-images;android-29;google_apis;x86_64                                              | 8            | Google APIs Intel x86 Atom_64 System Image                          
  system-images;android-29;google_apis_playstore;x86                                       | 8            | Google Play Intel x86 Atom System Image                             
  system-images;android-29;google_apis_playstore;x86_64                                    | 8            | Google Play Intel x86 Atom_64 System Image                          
  system-images;android-Q;android-tv;x86                                                   | 1            | Android TV Intel x86 Atom System Image                              
  tools                                                                                    | 26.1.1       | Android SDK Tools                      
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

The following Android Virtual Devices could not be loaded:
    Name: Pixel_3_API_28
    Path: /home/rahul/.android/avd/Pixel_3_API_28.avd
   Error: Google pixel_3 no longer exists as a device
Available devices definitions:
id: 0 or "tv_1080p"
    Name: Android TV (1080p)
    OEM : Google
    Tag : android-tv
---------
id: 1 or "tv_720p"
    Name: Android TV (720p)
    OEM : Google
    Tag : android-tv
---------
id: 2 or "wear_round"
    Name: Android Wear Round
    OEM : Google
    Tag : android-wear
---------
id: 3 or "wear_round_chin_320_290"
    Name: Android Wear Round Chin
    OEM : Google
    Tag : android-wear
---------
id: 4 or "wear_square"
    Name: Android Wear Square
    OEM : Google
    Tag : android-wear
---------
id: 5 or "Galaxy Nexus"
    Name: Galaxy Nexus
    OEM : Google
---------
id: 6 or "Nexus 10"
    Name: Nexus 10
    OEM : Google
---------
id: 7 or "Nexus 4"
    Name: Nexus 4
    OEM : Google
---------
id: 8 or "Nexus 5"
    Name: Nexus 5
    OEM : Google
---------
id: 9 or "Nexus 5X"
    Name: Nexus 5X
    OEM : Google
---------
id: 10 or "Nexus 6"
    Name: Nexus 6
    OEM : Google
---------
id: 11 or "Nexus 6P"
    Name: Nexus 6P
    OEM : Google
---------
id: 12 or "Nexus 7 2013"
    Name: Nexus 7
    OEM : Google
---------
id: 13 or "Nexus 7"
    Name: Nexus 7 (2012)
    OEM : Google
---------
id: 14 or "Nexus 9"
    Name: Nexus 9
    OEM : Google
---------
id: 15 or "Nexus One"
    Name: Nexus One
    OEM : Google
---------
id: 16 or "Nexus S"
    Name: Nexus S
    OEM : Google
---------
id: 17 or "pixel"
    Name: Pixel
    OEM : Google
---------
id: 18 or "pixel_c"
    Name: Pixel C
    OEM : Google
---------
id: 19 or "pixel_xl"
    Name: Pixel XL
    OEM : Google
---------
id: 20 or "2.7in QVGA"
    Name: 2.7" QVGA
    OEM : Generic
---------
id: 21 or "2.7in QVGA slider"
    Name: 2.7" QVGA slider
    OEM : Generic
---------
id: 22 or "3.2in HVGA slider (ADP1)"
    Name: 3.2" HVGA slider (ADP1)
    OEM : Generic
---------
id: 23 or "3.2in QVGA (ADP2)"
    Name: 3.2" QVGA (ADP2)
    OEM : Generic
---------
id: 24 or "3.3in WQVGA"
    Name: 3.3" WQVGA
    OEM : Generic
---------
id: 25 or "3.4in WQVGA"
    Name: 3.4" WQVGA
    OEM : Generic
---------
id: 26 or "3.7 FWVGA slider"
    Name: 3.7" FWVGA slider
    OEM : Generic
---------
id: 27 or "3.7in WVGA (Nexus One)"
    Name: 3.7" WVGA (Nexus One)
    OEM : Generic
---------
id: 28 or "4in WVGA (Nexus S)"
    Name: 4" WVGA (Nexus S)
    OEM : Generic
---------
id: 29 or "4.65in 720p (Galaxy Nexus)"
    Name: 4.65" 720p (Galaxy Nexus)
    OEM : Generic
---------
id: 30 or "4.7in WXGA"
    Name: 4.7" WXGA
    OEM : Generic
---------
id: 31 or "5.1in WVGA"
    Name: 5.1" WVGA
    OEM : Generic
---------
id: 32 or "5.4in FWVGA"
    Name: 5.4" FWVGA
    OEM : Generic
---------
id: 33 or "7in WSVGA (Tablet)"
    Name: 7" WSVGA (Tablet)
    OEM : Generic
---------
id: 34 or "10.1in WXGA (Tablet)"
    Name: 10.1" WXGA (Tablet)
    OEM : Generic
Available Android targets:
----------
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
