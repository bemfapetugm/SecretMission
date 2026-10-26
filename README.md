# Secret Mission — Two-Person Private Messenger (UI prototype)

## Start quickly
1. Extract this folder.
2. Open `index.html` using VS Code Live Server.
3. Enter any nickname and a shared room code to view the interface.

## Critical limitation
This starter is a **front-end prototype only**. Messages and the room code are stored locally in the current browser. It does NOT deliver messages to the other person's device, and the room code does NOT secure a server. The browser-local file attachment links are temporary. Do not use it for sensitive messages as-is.

## For real two-person messaging
A production version needs a shared backend. Recommended: Firebase Authentication + Cloud Firestore + Firebase Storage.
- Give each participant a distinct authenticated account.
- Create one room with exactly two approved user IDs.
- Restrict Firestore reads/writes to those two user IDs with Security Rules.
- Upload attachments to Storage with rules enforcing room membership and file-size/type limits.
- Use Firestore realtime listeners for messages.
- For notifications, add Firebase Cloud Messaging or browser notifications while the app is open.
- Never rely on a secret URL or a client-side room code as access control.
- If end-to-end confidentiality is a requirement, implement a reviewed end-to-end encryption design; TLS/database rules alone are not end-to-end encryption.

No Firebase credentials are included. Setup must be completed in your own Firebase project before real messaging works.
