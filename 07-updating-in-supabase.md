# Module 7 - Updating in Supabase

# Deliverable - Supabase Dropdown Character Maker

| User should be able to . . .                                                         |             |
| :----------------------------------------------------------------------------------- | ----------: |
| Visit the deployed pages on GitHub pages, with link in the About section of the Github repo |    1 |

| Events                                                                                |             |
| :----------------------------------------------------------------------------------- | ----------: |
| On the home page (`'/'`), Login and Signup using the login and signup form. On success, redirect to the `/character` page   |        1 |
| Logout by clicking the logout button                                                       |        1 |
| If a non-logged-in user tries to visit the character page, redirect them to the login page | 1 |
| On the character page load, fetch the character from supabase and render their details (including all catchphrases) to the page         |        1 |
| On change of the dropdown, update the character in supabase. Then fetch from supabase to update the UI to show the right image |     1 |
| On click of the catchphrase button, update the character in supabase. Then fetch from supabase to update the UI to show the right image. Note that this will require you to keep track of the state of the catchphrases locally in state. |     1 |
| On any dropdown change, see displayed how many times each dropdown has been changed in the current session (NOT tracked in supabase)   |           1 |

| Functions                                                                                |             |
| :----------------------------------------------------------------------------------- | ----------: |
| AUTH: `getUser()` : return currently logged in user |1|
| AUTH: `checkAuth()` : redirect the user to login if nobody is currently not logged in |1|
| ASYNC AUTH: `signupUser()` : create a new user in superbase and return user |1|
| ASYNC AUTH: `signinUser()` : log into superbase and return currently logged in user |1|
| ASYNC / DOM: `fetchAndRenderCharacter()` : fetches character and sets the images
| ASYNC: `fetchCharacter()` : fetches character for currently logged in user from supabase
| ASYNC: `updateHead(newHead)` : updates head of character for currently logged in user from supabase
| ASYNC: `updateMiddle(newMiddle)` : updates middle of character for currently logged in user from supabase
| ASYNC: `updateBottom(newBottom)` : updates bottom of character for currently logged in user from supabase
| ASYNC: `updateCatchphrases(newCatchphrases)` : updates catchphrases of character for currently logged in user from supabase
