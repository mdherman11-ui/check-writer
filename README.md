# Check Writer

A private check-printing app and check register for DocuGard bottom-check stock (check on the bottom, two stubs above). Install it on an iPhone from Safari with "Add to Home Screen" and it runs like an app, offline.

## Privacy

- This repository contains only the app's code. It never contains bank details or check history.
- Bank details and check history are stored only on the device that uses the app, encrypted with AES-256-GCM. The key comes from your passphrase (PBKDF2-SHA256, 600,000 rounds).
- The page's Content Security Policy blocks connections to any outside server. There are no analytics, trackers, or third-party scripts.
- The app locks after 5 minutes idle, or 2 minutes after you switch away from it.
- Backups are the same encrypted data in one file. Only your passphrase can open them.

## Deploy with GitHub Pages

1. Push these files to the `main` branch of a public repository. Only code is in the repo, so public is fine.
2. On GitHub, open the repository's Settings, then Pages. Under "Build and deployment", set Source to "Deploy from a branch", Branch to `main`, folder `/ (root)`, and click Save.
3. After a minute or two the app is live at `https://<your-username>.github.io/<repo-name>/`.

## Install on iPhone

1. Open the Pages link in **Safari**.
2. Tap Share, then **Add to Home Screen**.
3. Open it from the home screen and create your passphrase. Store the passphrase in your password manager. There is no way to recover it.

## First-time setup

1. **Accounts:** enter your bank details from a real check.
2. **Printer, Step 1:** print the measuring sheet on plain paper. Measure it with a ruler and enter the four numbers.
3. **Printer, Step 2:** print the edge test. If the bottom 3/16 in line is missing but the top one printed, turn on "Print upside down" and load check paper with the check end going in first.
4. **Printer, MICR font:** load an E-13B MICR font file, such as the free GnuMICR, from the Files app.
5. **Write:** print a VOID test on plain paper. Hold it over a blank check sheet against a window and fine tune if needed.
6. Take a VOID check printed on real check stock to your bank and ask them to confirm they can read it.
7. **Security:** save a backup to iCloud Drive. Repeat this every so often.

## Updating the app

Edit the files, then change `CACHE` in `sw.js` (for example to `check-writer-v1.0.1`) so installed copies pick up the new version. Your data on the phone is not affected by updates.
