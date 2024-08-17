## hacker-friendly-app

This web app, using Firebase, aims to demonstrate common Firebase security flaws by creating a hack-prone app. It has goals for noting and increasing awareness of often overlooked Firebase security risks and teaching some methods of spotting and countering them.

Advanced sections and demos will indicate using Firebase Custom Claims and the Firebase Admin for increased Firebase security.

### Usage

- Read the **"app/README.md"** file For more information about app installation and setup.

### Table of Contents

- [Intoduction](#hacker-friendly-app)
- [The Hack-Prone Quotes of the Day App](#the-hack--prone-quotes-of-the-day-app)
- [Deployment With GitHub Actions](#deployment-with-github-actions)

## The Hack-Prone Quotes of the Day App

- A simple Firebase web app that displays and manages "quotes of the day."
- It uses "only" Firebase with insecure, hacker-friendly security rules, providing an inviting and welcoming atmosphere for hackers to wreak havoc.
- Demonstrates using Cross-Site-Scripting (XSS) attacks

### Requirements

- Login Authentication using Google Sign-in
- Multiple signed-in users can edit the quote's content.
- Private UIs (requires sign-in):
   - View the quotes of the day.
      > Display the quotes as "HTML".
   - Add/Edit the quotes of the day.
      > Use a What-You-See-Is-What-You-Get (WYSIWYG) editor for encoding the quotes in a bullet list.
- Public "quotes of the day" board displaying three (3) inspirational quotes in a bullet list
   > Display the quotes as "HTML".
- Only use Firebase for the backend and nothing else.
- The app runs as a static website hosted on GitHub Pages (or other static-hosting).

### Schemas

#### Quote

There is only one **Quote** object which signed-in users can edit to update the "quotes of the day".

| field | Type | Description |
| --- | --- | --- |
| content | String | Three (3) quotes for the day in a bullet list, wrapped in semantic `<ul>` / `<ol>`, `<li>` HTML (bullet list) tags |
| theme | String | Quotes theme i.e., "technology", "nature", "ai", etc. |
| date_updated | Timestamp| Date the content was created/updated |
| updated_by | String | User ID |

#### User

For simplicity, signing in with Google using the Firebase Authentication Google Sign-In provider will create the hacker-friendly app's **Users** (content editors). They will have no Firestore document for managing and tracking users.

## Deployment With GitHub Actions

The app uses GitHub Actions to deploy to a **development** environment (Firebase Hosting + Firestore) on push or updates to the `dev` branch. It deploys to a **production** environment (GitHub Pages + Firestore) on creation of a new Release/Tag from the `master` branch.

Add the following GitHub Secrets to facilitate deployment to the **development** and **production** environments:

### Firebase Project

| Development | Production | Description |
| --- | --- | --- |
| DEV_FIREBASE_WEB_API_KEY | PROD_FIREBASE_WEB_API_KEY | Firebase web API key from the Firebase Project Settings configuration file. |
| DEV_FIREBASE_WEB_AUTHDOMAIN | PROD_FIREBASE_WEB_AUTHDOMAIN | Firebase web auth domain key from the Firebase Project Settings configuration file. |
| DEV_FIREBASE_WEB_PROJECT_ID | PROD_FIREBASE_WEB_PROJECT_ID | Firebase web project ID from the Firebase Project Settings configuration file. |
| DEV_FIREBASE_WEB_STORAGE_BUCKET | PROD_FIREBASE_WEB_STORAGE_BUCKET | Firebase web storage bucket key from the Firebase Project Settings configuration file. |
| DEV_FIREBASE_WEB_MESSAGING_SENDER_ID | PROD_FIREBASE_WEB_MESSAGING_SENDER_ID | Firebase web messaging sender ID from the Firebase Project Settings configuration file. |
| DEV_FIREBASE_WEB_APP_ID | PROD_FIREBASE_WEB_APP_ID | Firebase web web app key from the Firebase Project Settings configuration file. |
| DEV_FIREBASE_WEB_MEASUREMENT_ID | PROD_FIREBASE_WEB_MEASUREMENT_ID | Firebase web measurement ID from the Firebase Project Settings configuration file. |

### Others

| GitHub Secret | Description |
| --- | --- |
| FIREBASE_PROJECT_DEV | Firebase project name used by the **development** environment. |
| FIREBASE_PROJECT_DEV_HOSTING | Firebase Hosting domain name under the `FIREBASE_PROJECT_DEV` project. |
| FIREBASE_TOKEN | Firebase deployment token. |

@weaponsforge<br>
20240816
