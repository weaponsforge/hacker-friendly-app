## hacker-friendly-app

This web app, using Firebase, aims to demonstrate common Firebase security flaws by creating a hack-prone app. It has goals for noting and increasing awareness of often overlooked Firebase security risks and teaching some methods of spotting and countering them.

Advanced sections and demos will indicate using Firebase Custom Claims and the Firebase Admin for increased Firebase security.

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

For simplicity, signing in with Google using the Firebase Authentication Google Sign-In provider will the hacker-friendly app's **Users** (content editors). They will have no Firestore document for managing and tracking users.

@weaponsforge<br>
20240816
