NWO STRIKERS TEAM MANAGEMENT PORTAL

Firebase configuration has been inserted into index.html for project nwo-strikers.

FILES
- index.html: portal website, connected to Firebase project nwo-strikers
- firestore.rules: Firestore security rules
- README.txt: setup and account instructions

ALREADY COMPLETED
- Firebase web app registered
- Email/Password sign-in enabled
- Firestore database created in asia-south2
- Admin authentication user created
- Admin profile document created at users/{your-auth-uid}

IMPORTANT NEXT STEPS
1. In Firestore > Rules, confirm the published rules match firestore.rules in this package.
2. Create each leader/co-leader account in Firebase Authentication > Users.
3. For each account, create a Firestore document in collection users with document ID exactly equal to that account's Authentication UID.
4. Profile fields:
   Admin: displayName (string), role (string: admin), teamId (string: none)
   Co-leader: displayName (string), role (string: coleader), teamId (string: none)
   Leader: displayName (string), role (string: leader), teamId (string: matching team ID)
5. Team IDs: warbringers, howlers, destroyers, protectors, creators, bullseye.
6. Upload index.html to GitHub Pages or another HTTPS static host.

SECURITY
- Never allow users to choose their own role or team.
- Do not share admin credentials.
- The Firebase web config includes a public API key; Firestore Security Rules and Authentication protect data access.
- Test with one leader account before inviting all users.

FEATURES
- Daily and weekly contribution reports: boosts, Squad Rush flags, ABR wins, Alliance Race wins.
- Report history and admin/co-leader team overview.
- Leaders can access only their assigned team.
- The portal cannot automatically read Hitwicket game stats or send WhatsApp messages.
