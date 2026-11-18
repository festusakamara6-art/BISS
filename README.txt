BENEVOLENT ISLAMIC SECONDARY SCHOOL, MAKENI - WEBSITE PROJECT

FOLDERS
  website/   index.html (the whole website) and logo.jpg
  database/  firestore.rules and database-structure.md

SET UP THE DATABASE (Firebase, free)
 1. console.firebase.google.com > Create project "biss-makeni".
 2. Register a Web app (</>) and copy the firebaseConfig values.
 3. Open website/index.html, find "STEP 1: PASTE YOUR FIREBASE CONFIG HERE" and replace the PASTE_ values.
 4. Build > Firestore Database > Create database (Production mode).
 5. Firestore > Rules: paste database/firestore.rules and Publish.
 6. Build > Authentication > Enable Email/Password > Add user festusamadukamara@gmail.com with a STRONG password.
 7. Authentication > Settings > Authorized domains: add your GitHub address (e.g. festus6-art.github.io).

PUBLISH ON GITHUB PAGES
 1. github.com > New repository "biss-makeni" (Public, license: None).
 2. Upload everything inside the website folder (index.html, logo.jpg).
 3. Settings > Pages > Deploy from branch: main, / (root) > Save.
 4. Live at https://YOUR-USERNAME.github.io/biss-makeni/

ADMIN
 Footer > Admin Dashboard > log in with the admin email and your Firebase password.

SCHOOL PORTAL (students, teachers, parents)
 - Users create accounts from Login > "Create an account". Teachers need the staff code set in database/firestore.rules.
 - After changing firestore.rules, paste them in Firebase > Firestore > Rules and Publish.
 - Images are stored in Firestore (resized). Videos are added as YouTube / Google Drive links.
 - Virtual classroom opens a Jitsi Meet room in a new tab (teachers can share screen to present).

ADMISSION PAYMENT (Orange Money) + LOGIN TRACKING
 - Edit ADMISSION_FEE, ORANGE_NUMBER, ORANGE_NAME near the top of the script in website/index.html.
 - Applicants pay by Orange Money, then enter the transaction ID. Status starts as Pending; the admin sets Paid or Failed.
 - Admin dashboard > Users & Logins shows name, email, role, last login, login count, with search and filters.
 - Republish database/firestore.rules in Firebase after this update.

STUDENT VERIFICATION (current and past students)
 - Admin Dashboard > Current Students / Past Students: upload a CSV (see database/*-template.csv), add students one by one, and upload documents for each group.
 - A student can create an account only if admission number + full name (+ date of birth, if recorded) match the roster. Otherwise sign-up is refused.
 - Every login is checked again against the roster. Removed students lose access.
 - Verified students see their record and only the documents for their group (current or past).
 - Republish database/firestore.rules in Firebase after this update.
