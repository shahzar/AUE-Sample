# AUE Sample Xamarin Application 

## Source-code:
[https://www.dropbox.com/s/vkwgcm7r5kcv01m/AUE.7z?dl=0](https://www.dropbox.com/s/vkwgcm7r5kcv01m/AUE.7z?dl=0)

## Download APK:
[APK](https://www.dropbox.com/s/256vp54a5ij85hf/AUE_Sample.apk.7z?dl=0)

## Description:

### Features 
#### - Fetching data via REST API 
- Consuming REST API provided by Openweathermap & displaying the fetched data.

#### - Push Notification using GCM
- Chat application using Google Cloud Messaging, including Push Notifications.
- Install provided APK into multiple devices to test this out.



## Compilation
The Visual Studio Solution contains two projects, `AUELibrary` & `AUE Sample`.

`AUELibrary` is a PCL (Portable Class Library) project, containing the data-models & the code for fetching & consuming of REST Api. 

This exists as a seperate project so as to conform to the MVVM Architecture recommended by Xamarin, to seperate the domain layer into a PCL, so the same code can be reused when building for other platforms.

`AUE Sample` contains the main code for Android Platform, including all the Activities, and code related by it.

### - NuGet Package Dependencies
  - #### AUELibrary
    - Microsoft.Net.Http
    - Newtonsoft.Json
  - #### AUE Sample
    - Xamarin.Firebase.Common
    - Xamarin.GooglePlayServices.Basement    

## Project Structure
### - AUE Sample:
- Activities
  - `MainActivity` contains the main launcher activity
  - `MessageActivity` contains the GCM based chat
  - `WeatherActivity` displays the Weather Data of a hard coded location
- Broadcast receiver
  - `MessageBroadcastReceiver` handles broadcast message sent by `CustomFirebaseMessagingService`
- GCM Handlers
  - `CustomFirebaseMessagingService` handles incoming push messages
  - `CustomFirebaseIIDService` handles Firebase initialization
- View Adapters
  - `MessagesListAdapter` handles the messages list found in `MessageActivity` 
- Util 
  - `ImageHelper` helper class to download Image Bitmap from URL (Not yet used in the project)
