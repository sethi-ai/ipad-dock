# iPad Dock

A clock and calendar for an old iPad that sits on a desk or shelf. It works like iPhone StandBy: a big clock with the date on one side, a month calendar on the other, and a dim red night mode.

It is one HTML file with no ads, no account and no tracking. After the first load it runs with no internet.

## Set it up on the iPad

1. Open the page in Safari on the iPad.
2. Tap Share, then **Add to Home Screen**.
3. Open **Dock** from the home screen once while you are online. This saves a copy on the iPad.
4. Go to Settings, Display & Brightness, Auto-Lock, and choose **Never**.
5. Keep the iPad plugged in.

To stop stray taps, open Settings, Accessibility, Guided Access and turn it on. Then open Dock and triple-click the Home button to start it. Guided Access ends if the iPad restarts, so start it again after a restart.

## Controls

Tap the screen to show a small settings bar. It hides itself after a few seconds, or when you tap the screen again.

- **Clock:** 12 hour or 24 hour.
- **Layout:** Calendar (clock plus month calendar), Date only (a large clock with the day, date and year) or Focus (the day and clock fill the screen, with the date small in the footer). Tap the Layout button to cycle through them.
- **Mode:** Normal, Night (dim red text on black) or Desk (green terminal look on a dark green gradient). Tap the Mode button to cycle through them.

The iPad remembers your choices.

## Offline use

The page reads the iPad's own clock, so the time and date keep updating with no internet. A service worker saves the page the first time you open it from the home screen.

- Offline use needs iOS 11.3 or newer. That covers iPad Air, iPad mini 2 and later. Older iPads (iPad 2, 3 and 4) can still load the page, but they need Wi-Fi each time you open it.
- To test, open Dock from the home screen once online, turn on Airplane Mode, close the app fully and open it again.
- Leave Settings, General, Date & Time, **Set Automatically** on, and pick your time zone. The iPad corrects its clock whenever it is online.

## Battery

The page does almost nothing while it runs. It updates once a minute, which is about 1,400 wake-ups a day instead of 86,400 for a clock with seconds, and it redraws only what changed. It has no animations, no network requests and no background work. For that reason it has no seconds display.

The screen uses far more power than the page does, so these settings matter more:

- Lower the brightness in Control Center, and turn on Auto-Brightness in Settings, Display & Brightness.
- Turn off Bluetooth and Background App Refresh if you don't use them.
- Airplane Mode saves more power, but the iPad then can't correct its clock until you go back online.
- Desk mode is only a static colour gradient, so it costs no extra power.
- Dark colours save power only on OLED screens. Old iPads have LCD screens, so brightness is what counts.

## Compatibility

Written in plain HTML, CSS and ES5 JavaScript so it runs on the Safari that ships with iOS 12. Please open an issue with your iPad model and iOS version if something looks wrong.

## Change it

Everything is in `index.html`: colours are at the top of the style block, and the layout and script follow. When an iPad is online, Dock fetches the newest files each time you open it and refreshes its saved copy, so edits reach it on their own. If you add or rename files, list them in `sw.js` and change the `CACHE` name there.

## Credits and licence

Code: MIT, see `LICENSE`. Fonts (Barlow, Barlow Condensed and Share Tech Mono, embedded in `index.html`): SIL Open Font License 1.1, see `licenses/`.
