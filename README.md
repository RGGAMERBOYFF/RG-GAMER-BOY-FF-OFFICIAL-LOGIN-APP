# RG GAMER BOY FF — Login website

## Deploy
1. Upload the contents of this folder to the root of the GitHub Pages repository for `https://rggamerboyff.github.io/RG-GAMER-BOY-FF-OFFICIAL-APP/`.
2. Firebase Console → Authentication → Sign-in method: enable Google and Anonymous.
3. Firebase Authentication → Settings → Authorized domains: confirm `rggamerboyff.github.io` is present.
4. Realtime Database → Rules: review and publish `database.rules.json`.
5. Test Google sign-in on the deployed HTTPS URL, guest sign-in, refresh persistence, and sign-out.

## Important limitations before production
- Google popup is used first; redirect fallback is used if the browser blocks popups. `getRedirectResult` is processed on page load to avoid getting stuck on the Google screen.
- Google sessions use browser-local Firebase persistence. Guest sign-in has been removed.
- The Delete Account button appears only for Google-linked sign-ins and opens the supplied Google Form. The form submission is a request, not an automatic deletion.
- Add the real support email, confirm the Privacy Policy and Terms match actual practices, and set governing law before publishing.
- Username/password sign-in is supplied as `index2.html` and remains the original localStorage/SHA-256 implementation. The login button links to `./index2.html`.
- Do not put Firebase Admin SDK credentials in frontend files.
- The sample database rules only allow the exact profile fields written by `app.js`. If you change the data model, update and test rules together.
- Firebase Analytics is not initialized in this version; the measurement ID is retained in config only.

## Owner-supplied assets and destinations
- Logo image: `https://i.supaimg.com/cc740f2b-876c-4dd7-bbf2-16d636413b82/85320e1a-9a75-4178-90bb-a7f01267a661.png` (displayed upright with no CSS rotation).
- Account deletion request form: `https://docs.google.com/forms/d/e/1FAIpQLScPdr838eNtKeTrt40nIlzS9w-Sz7Hvsotf1-MZAlXI5JWXEw/viewform?usp=dialog`.
- Successful Google sign-in Continue destination: `./main.html`.
- Existing username/password site: `https://rggamerboyff.github.io/RG-GAMER-BOY-FF-2022-APP/`.


## Existing local page and music asset
- `index2.html` is included unchanged from the supplied username/password page. Its account storage, SHA-256 password hashing, and `./main.html` destination are unchanged.
- The username/password page references `atlasaudio-christmas-song-636082.mp3`. That MP3 was not present in the uploaded ZIP or the available saved source file, so keep the existing MP3 with that exact filename in the deployed site root for Winter Music playback to work.
- Keep the existing `main.html` in the same deployed site root; both login paths navigate to it locally.
