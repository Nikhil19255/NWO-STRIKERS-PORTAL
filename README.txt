NWO STRIKERS PORTAL V2

FILES
- index.html: replace the current repository index.html with this file.
- firestore.rules: replace the Firestore Rules with this file.

ROLE PROFILE DOCUMENTS
Collection: users
Document ID: Firebase Authentication UID

Admin:
{ "displayName": "NWO Admin", "role": "admin", "teamId": "none" }

Co-leader:
{ "displayName": "Co-leader name", "role": "coleader", "teamId": "none" }

Team leader:
{ "displayName": "Leader display name", "role": "leader", "teamId": "one of the six IDs" }

TEAM IDS
warbringers, howlers, destroyers, protectors, creators, bullseye

PERMISSIONS
- Admin and co-leaders can view all teams, edit all team rosters, submit reports for any team, and view all submitted reports.
- A team leader can view the roster and edit only the team whose ID is in their users/{uid} profile.
- A team leader can submit reports only for their assigned team.
- Team leaders cannot read submitted reports (including their own), and cannot edit/delete submitted reports.
- Users cannot edit their own role profile through the portal.

FIRST ADMIN LOGIN AFTER DEPLOYMENT
The first Admin/Co-leader login creates any missing teams/{teamId} documents using the default roster. Existing team documents are never overwritten.

DEPLOY
1. Back up the current index.html in GitHub by downloading it or copying it to a safe note.
2. Replace repository index.html with this package's index.html and commit.
3. In Firebase Console > Firestore Database > Rules, replace the rules with firestore.rules contents and Publish.
4. Open the GitHub Pages site and sign in with the existing Admin account. This seeds the six team documents.
5. Test editing a team, refresh the page, and confirm the changes remain.
6. Create leader accounts in Firebase Authentication, then create users/{their UID} profiles with role=leader and their exact teamId.
7. Create co-leader accounts with role=coleader and teamId=none.

IMPORTANT
- Do not share passwords or private service-account credentials.
- Firebase web config is used by the browser; Firestore Rules are what enforce access.
- Do not give leader accounts the admin or coleader role.
- Before applying new rules, make sure the existing Admin profile document is correct.
