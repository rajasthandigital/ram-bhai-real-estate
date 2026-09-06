# Real Estate Agent Ram Bhai — V10 Business System

यह version localStorage demo नहीं है। यह Firebase Auth + Firestore के लिए बनाया गया production-style system है।

## इसमें क्या है
- Customer Mobile OTP login
- Google/Gmail login
- Buyer requirement flow
- Seller / I Want to Sell flow
- Buyer/Seller data private Firestore में
- Agent-only admin dashboard
- Property inventory: Available / Booked / Sold
- Client को केवल availability दिखाई जाती है; exact address, private notes और internal data नहीं
- Meeting/request records cloud में save
- WhatsApp notification shortcut
- Installable fullscreen PWA
- Firestore security rules included

## एक बार Firebase setup करना होगा
1. Firebase Console में नया project बनाइए.
2. Web App add कीजिए और उसकी config `firebase-config.js` में डालिए.
3. Authentication → Sign-in methods में:
   - Phone
   - Google
   - Email/Password (Agent Admin के लिए)
   enable करें.
4. Authentication → Settings → Authorized domains में अपना GitHub Pages domain जोड़ें.
5. Firestore Database बनाइए और `firestore.rules` publish करें.
6. `firebase-config.js` में Ram Bhai का admin email डालें और यही exact email rules में भी डालें.
7. उसी admin email से Firebase Authentication में Agent account बनाइए.
8. GitHub Pages पर पूरा folder upload करें.

## Important
`firebase-config.js` में API key public होना सामान्य है; असली protection Firestore Rules और Firebase Authentication से आती है.

## Cloud notifications
WhatsApp shortcut अभी तुरंत काम करता है. True browser push notifications के लिए Firebase Cloud Messaging (FCM) setup + VAPID key और service worker configuration अलग से जोड़ना होगा.

## Business use
इस version में requests एक device के localStorage में नहीं रहतीं; Firebase Firestore में cloud पर save होती हैं, इसलिए Agent और customers अलग-अलग devices से data use कर सकते हैं.
