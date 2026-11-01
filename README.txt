MYDIARY — setup guide

FILES
- index.html: the complete responsive website.
- firestore.rules: rules that keep each user's entries private.

1) FIREBASE AUTHENTICATION
Firebase Console > Authentication > Sign-in method > Google > Enable.
In Authentication > Settings > Authorized domains, add your published website domain
(for example: YOUR-USERNAME.github.io). Do not add https:// or a page path.

2) FIRESTORE RULES
Firebase Console > Firestore Database > Rules.
Replace the rules with the contents of firestore.rules and click Publish.
These rules let each signed-in user read/write only their own entries.

3) GITHUB PAGES
Create/open your GitHub repository, upload index.html, and make sure the filename
is exactly index.html. Enable GitHub Pages in repository Settings > Pages.

4) TEST
Open the published site, sign in with Google, and create a diary entry.
Use a second Google account to confirm it cannot see the first account's entries.

IMPORTANT
- The Firebase web config in index.html is designed to be used in a browser.
  It is not a private server password. Keep your Google account password and any
  Firebase service-account/private keys secret.
- This first version includes Google sign-in, private text entries, search, edit/delete,
  entry dates, entry counts, and dark mode.
- Photo uploads and calendar month view are not included yet; they need extra setup.
- If Google sign-in reports auth/unauthorized-domain, add your exact published host
  under Authentication > Settings > Authorized domains.
