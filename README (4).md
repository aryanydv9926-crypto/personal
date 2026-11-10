# DairyFlow

Milk dairy management: admin + customer panels. Plain HTML/CSS/JS + Firebase (Auth + Firestore, free Spark plan, no Storage).

Files: `index.html` (page), `style.css` (design), `app.js` (all logic + Firebase; config at the top), `firestore.rules` (security), `firebase.json`.

## One-time Firebase setup (console.firebase.google.com > project abcd-11d9d)
1. Firestore > Rules > paste `firestore.rules` > Publish.
2. Authentication > Users > Add user (admin email + password). Copy the User UID.
3. Firestore > Start collection `admins` > Document ID = that UID > field `role` = `admin`.
4. Authentication > Settings > Authorized domains > Add `YOUR-GITHUB-USERNAME.github.io` (needed for GitHub Pages).

## Run locally
Open the folder in VS Code > install "Live Server" > right-click `index.html` > Open with Live Server. (Do not double-click the file: login will not work from file://.)

## Publish on GitHub Pages
```
git init
git add .
git commit -m "DairyFlow with Firebase"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/dairyflow.git
git push -u origin main
```
Then on GitHub: Settings > Pages > Source: Deploy from branch > main / (root) > Save. Your site: https://YOUR-USERNAME.github.io/dairyflow/

## First use
Admin login > Milk Prices (set prices first) > Customers > Add customer (give them the email + password you set) > Daily Milk Entries.
Google sign-in is not used; accounts without an admin/customer record are refused.
