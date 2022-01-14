# Lecture 10 - User profiles

Imagine you wanted to do a list detail page for an app's users.

You'll soon find that supabase doesn't let us query the users table directly.

That means we'll need to create a parallel table to store used data. Let's call it `profiles`, which has a foreign key that points to the `users` table in supabase. 

Having a `profiles` table gives us the added benefit of being able to add more properties to our users.

```js
{
    email: '',
    user_id: '',
    karma: '',
    avatar: '',
}
```

This also makes it possible for us to have a robust social media app. Imagine for example a reddit clone with a `posts` table. This table would point to the profiles with a `recipient_id`.