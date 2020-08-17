# Android-Unity-Intergration
- - - - - - - - - - - - - - - 
1. Build and Run your Unity project.

2. Open File - New - import Module... and add unityLibrary folder.

3. Open File - Project Structure and select 'Dependencies'. 
   Add 'unityLibrary' as Module Dependency to 'app'.

4. Add code below to build.gradle(Project: ~) - allproject - repositories
  ```
  flatDir {
    dirs "${project(':unityLibrary').projectDir}/libs"
  }
  ```

5. Remove <intent-filter>...</intent-filter> from AndroidManifest.xml in unityLibrary  

6. if android.content.res.Resources$NotFoundException: String resource ID #0x0 occurs, Add code below to app - res - values - strings.xml
  ```
  <string name="game_view_content_description">Game view</string>
  ```

7. if NDK error occurs, Add code below to bulld.gradle(app) - android - defaultConfig 
  ```
  ndk {
    abiFilters 'armeabi-v7a'
  }
  ```
