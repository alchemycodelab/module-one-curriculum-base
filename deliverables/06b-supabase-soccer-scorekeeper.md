# Deliverable 06 - Supabase Soccer Scorekeeper

[Buggy Supabase Soccer Scorekeeper](https://github.com/alchemycodelab/buggy-js-soccer-scorekeeper-supabase)

[Half Baked Supabase Soccer Scorekeeper](https://github.com/alchemycodelab/half-baked-js-soccer-scorekeeper-supabase)

### Live Example:
https://alchemycodelab.github.io/js-soccer-scorekeeper/

![](../assets/soccer-scorekeeper.png)

| User should be able to . . .                                                         |             |
| :----------------------------------------------------------------------------------- | ----------: |
| Visit the deployed pages on GitHub pages, with link in the About section of the Github repo|        1 |
| On the home page (`'/'`), Login and Signup using the login and signup form. On success, redirect to the `/games` page   |        1 |
| Logout by clicking the logout button                                                       |        1 |
| If a non-logged-in user tries to visit the games page, redirect them to the login page | 1 |
| On the games page load, see a form and empty current game div                              |        1 |
| On the games page load, fetch all past games and render them to the past games div         |        1 |
| On submit, add the team names to the current game div                                      |        1 |
| On clicking add or subtract, increment and decrement the correct score in the current game div|     1 |
| On clicking finish, empty the current game div, and use supabase to add the current game to the database. |1|
| On clicking finish, clear the past games div, then fetch all past games from supabase and render them in the past games div. |1|

| Functions                                                              |             |
| :----------------------------------------------------------------------------------- | ----------: |
| IMPURE: `updateCurrentGameEl()` | 1|
| IMPURE: `displayAllGames()` : clears out and appends to games div | 1|
| PURE: `renderGame(game)` : returns DOM node | 1|
| PURE: `renderTeam(name, score)` :  return DOM node | 1|
| ASYNC: `createGame(game)` : creates a game for currently logged in user in supabase |1|
| ASYNC: `getGames()` : returns games for currently logged in user from supabase |1|
