# Lecture 7 - Updating in Supabase

## Async/Await and updating in supabase 

Remember to always use `.match({ user_id: client.auth.session().user.id })`  for user-created entities, especially in the 'half-baked'assignments.