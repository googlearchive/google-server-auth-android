# google-server-auth-android

## Overview
This sample application demonstrates the following features:

  * [Google Sign-In](https://developers.google.com/identity/sign-in/android/)
  * [Retrieving server auth code for offline access](https://developers.google.com/identity/sign-in/android/backend-auth)

## Prerequisites
To run this sample you will need the following:

  * An Android device running Android 2.3 or higher that has the Google Play Store
  * [Android Studio](https://developer.android.com/sdk/index.html)
  * The Google Play Services SDK (install in Android Studio via Tools > Android > SDK Manager)

## Set Up
In order to use Google Sign-In in your application, you will need to register your application
in the Google Developers Console.

1. Go to the [Google Developers Console](https://console.developers.google.com/).
1. Click **Create Project**.  Then enter a **Project name** and click **Create**.
1. In the left sidebar, click **APIs & auth**.  Find and enable the **Google+ API**.
1. In the left sidebar, select **Consent Screen**.  Fill out all required fields and click **Save**.
1. In the left sidebar, select **Credentials**:
    1. Click **Create a new Client ID**:
    1. Select **Installed Application** and then select **Android**.
    1. Enter `com.google.android.gms.identity.quickstart` as your package name.
    1. Enter the SHA1 of your debug keystore file.  If you don't know how to get that, execute
    the `keytool` command on [this page](https://developers.google.com/+/mobile/android/samples/quickstart-android#step_1_enable_the_google_api).
    1. Click **Create Client ID**.
    
## Run
Now that you have created a Client ID, you are ready to run the sample app.  Import the
app into Android Studio and run it on your Android device,

## Offline Access
This app demonstrates how to get a an ID token and server auth code during sign-in, but you will
notice that some values are not filled in.  If you would like to test the sample with your own
webserver, create a Client ID for your server in the **same project** as the Android Client ID.
Then, change the following values:

* `MainActivity.java`:
    * Change `WEB_CLIENT_ID` to the Client ID of your web server.
* `ServerAuthHandler.java`:
    * Change `SERVER_BASE_URL` to the base URL of your web server (like "https://example.com")
    * Change `EXCHANGE_TOKEN_URL` to the path on your web server where the Android application
    should send the server auth code and id token.
    * Change `SELECT_SCOPES_URL` to the path on your server where the Android client can get
    the list of scopes required by your server for offline access.
