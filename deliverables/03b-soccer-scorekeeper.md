# Deliverable 03 - Soccer Scorekeeper

### Live Example:
https://dpcairns.github.io/soccer-scorekeeper/

| User should be able to . . .                                                         |             |
| :----------------------------------------------------------------------------------- | ----------: |
| Visit the deployed pages on GitHub pages, with link in the About section of the Github repo|        1 |

| Events                                                                               |             |
| :----------------------------------------------------------------------------------- | ----------: |
| On load, see a form and empty current game div                                             |        1 |
| On submit, add the team names to the current game div                                      |        1 |
| On clicking add or subtract, increment and decrement the correct score in the current game div|     1 |
| On clicking finish, empty the current game div and add the current game to the "past games" div. All past games should be visible in this div. |1|

| Functions                                                              |             |
| :----------------------------------------------------------------------------------- | ----------: |
| IMPURE: `displayCurrentGameEl()` | 1|
| IMPURE: `displayAllGames()` : clears out and appends to games div | 1|
| PURE: `renderGame(game)` : returns DOM node | 1|
| PURE: `renderTeam(name, score)` :  return DOM node | 1|
