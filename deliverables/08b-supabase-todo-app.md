# Deliverable 08 - Supabase Todo App

[Buggy Supabase Todo App](https://github.com/alchemycodelab/buggy-js-todo-supabase)

[Half Baked Supabase Todo App](https://github.com/alchemycodelab/half-baked-js-todo-supabase)

### Live Example:
https://alchemycodelab.github.io/js-todo-supabase/

![](../assets/todos.png)

| User should be able to . . .                                                         |             |
| :----------------------------------------------------------------------------------- | ----------: |
| Visit the deployed pages on GitHub pages, with link in the About section of the Github repo |    1 |
| See completed todos styled differently from incomplete todos                                   |        1 |

| Events                                                                                |             |
| :----------------------------------------------------------------------------------- | ----------: |
| On the home page (`'/'`), Login and Signup using the login and signup form. On success, redirect to the `/todos` page   |        1 |
| Logout by clicking the logout button                                                       |        1 |
| If a non-logged-in user tries to visit the todos page, redirect them to the login page     |       1 |
| On the todos page load, fetch the todos from supabase and render them to the page         |        1 |
| Add a todo to supabase by using the input and button.                                     |        1 |
| When a todo is added, clear out the todo list and render the updated list of todos        |        1 |
| When a user clicks a todo, it becomes complete. Update this state in supabase, clear out the todo list, and re-fetch the updated todos.        |        1 |
| When a user clicks delete all todos, all todos. Update this state in supabase, clear out the todo list, and re-fetch the updated todos.        |        1 |


| Functions                                                                                |             |
| :----------------------------------------------------------------------------------- | ----------: |
| ASYNC: `createTodo(todo)` : create a todo in supabase for the logged-in user |1|
| ASYNC: `deleteAllTodos(todo)` : delete all todos  in supabasefor the logged-in user |1|
| ASYNC: `getTodos()` : get all todos in supabase for the logged-in user |1|
| ASYNC: `completeTodo(id)` : complete this todos in supabase for the logged-in user |1|
