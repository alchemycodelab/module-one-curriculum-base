

# Module 5 - Games as State

This is kind of a 'put it all together' module. You don't have much new to learn. However, the assignment itself is complex, because you have a lot of state you need to manage.

Some advice for complex assignments:
1) Remember to make a plan. You might have squeaked by with no plan so far, but it's more likely to catch up with you here if you try to 'just figure it out at you go'.
1) Think carefully about you HTML elements and their relationship to events.
    - Make a list: for each event in your app, ask what HTML element will the event be attached to?
1) Think carefully about your events and their relationship to state.
    - Make a list: for each event in your app, what state will change and how will it change?
1) Think carefully about the relationship between HTML elements and the state.
    - Make a list: for each item in state, what HTML elements will I need to generate to represent this state?
    - Make a list: when does state change? Every item on this list counts as a time when you need to update the DOM (otherwise the user won't know that state changed)

# Deliverable - Mushroom Festival

# Mushroom Festival

| User should be able to . . .                                                         |             |
| :----------------------------------------------------------------------------------- | ----------: |
| Visit the deployed pages on GitHub pages, with link in the About section of the Github repo|     1 |

| Events                                                                                |             |
| :----------------------------------------------------------------------------------- | ----------: |
| On load, see some mushrooms and default friends on the page                                |        1 |
| On clicking the 'forage' button, launch an alert telling the user if they found a mushroom. 50% of the time, the user should succeed.  | 1 |
| The number of mushrooms should be visible on the table.                                      |        1 |
| On clicking a friend, a mushroom should vanish from the table, and the friend should become more satisfied. Satisfaction level should be visible to the user as different emojis |     1 |
| On clicking a friend, if that friend is completely satisfied, they can eat no more mushrooms. Also, if you try to feed a friend and there are no mushrooms, user should get an alert telling them to go forage for another mushroom. |1|
| Click on the 'invite' button to create a new (unsatisfied) friend (with a random default name if none is provided) and add them to the page | 1 |

| Functions                                                                                |             |
| :----------------------------------------------------------------------------------- | ----------: |
| PURE: `findFriendByName(name, friends)` : return friend object` |1|
| IMPURE: `addFriend(name, friends)` |1|
| PURE: `renderMushroom()` : return DOM node` |1|
| PURE: `renderFriend(friend)` : return DOM node` |1|
| IMPURE: `renderFriends(friends)` : clears and appends to friend list DOM node`
