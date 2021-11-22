# Deliverable 05 - Supabase Dog Adoption App

[Buggy Supabase Adopt a Dog](https://github.com/alchemycodelab/buggy-js-adopt-a-dog)

[Half Baked Supabase Adopt a Dog](https://github.com/alchemycodelab/half-baked-js-adopt-a-dog)

### Live Example:
https://alchemycodelab.github.io/js-adopt-a-dog/


| User should be able to . . .                                                         |             |
| :----------------------------------------------------------------------------------- | ----------: |
| Visit the deployed pages on GitHub pages, with link in the About section of the Github repo|        1 |


| Events                                                                                |             |
| :----------------------------------------------------------------------------------- | ----------: |
| On load on the home page, see a list of dogs (names and breed image), fetched from supabase                               |        1 |
| On clicking a dog, user should be taken to that dog's detail page.  | 1 |
| Detail page should get the id from the URL and use that id to fetch that dog from supabase.                                      |        1 |
| Detail page should show the user details about the dog (including age, breed, and description) |     1 |

| Functions                                                                                |             |
| :----------------------------------------------------------------------------------- | ----------: |
| PURE: `renderDogCard(dog)` : return DOM node |1|
| IMPURE: `renderDogDetail(dog)` : return DOM node |1|
| ASYNC: `fetchDogs()` : return array of dogs from supabase |1|
| ASYNC: `fetchDog(id)` : return single dog from supabase |1|
