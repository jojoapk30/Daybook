# Daybook (native Android app)

Your Daybook web app wrapped as a real Android app with Capacitor.
Alarms are scheduled with Android's own alarm system, so they fire even when the app is closed.

## Easiest way (phone or computer, no installs)
1. Create a free GitHub account and a new repository.
2. Upload everything in this folder (keep the `.github` folder).
3. Open the repository's **Actions** tab, choose **Build Android APK**, tap **Run workflow**.
4. When it finishes (about 5 minutes), open the run and download **daybook-apk**.
5. Unzip it, open `app-debug.apk` on your phone and allow "install unknown apps".

## Build on a computer
Needs Node 20+, Java 17 and Android Studio.

    npm install
    npm run android:add
    npm run open        # opens Android Studio, press Run

After editing `www/index.html`, run `npm run sync` and rebuild.

## First launch
Allow notifications when asked. If Android asks for exact alarms, allow it.
Then open Settings in the app and tap **Test alarm sound**: a notification should arrive 5 seconds later.
On some phones (Samsung, Xiaomi, Tecno, Infinix) also set Daybook's battery use to "Unrestricted" so alarms are not delayed.

## How alarms behave
- Each reminder schedules 5 alarm notifications, one per minute, until you open the app and tap Stop or Snooze.
- With the app open, the full-screen ringing alarm appears at the exact time.
- If the phone is locked, you get a loud notification (default notification sound, vibration) rather than a looping ringtone.
  A looping full-screen alarm over the lock screen needs custom Kotlin code.

Android only. An iPhone version needs a Mac and Xcode.
