# Supabase Notes

- Cohort will use Alchemy-supplied supabase keys and URLs for all "batteries-included" assignments
    - IMPORTANT: always supply a user_id when fetching and creating items.
    - Otherwise, uh, this kind of doesn't work since you need to only be able to fetch the items your users created, and not items that _all the other students in the cohort_ created.

---

- For 'from scratch' deliverables, students will create their own supabase instances. 

- Tables will look something like the below examples.

# 🍳 Sample data models for 'from scratch' deliverables:

## Beanie babies List/Detail

### Beanie Baby 
- because this deliverable has no way to create a beanie baby, you will manually enter these in the supabase dashboard
```js
{
    id: 1,
    name: '',
    birthday: '',
    picture_url: '',
    description: '',
}
```

## Poll Maker 

### Poll
```js
{
    id: 1,
    question: '',
    option1: '',
    option2: '',
    votes1: 0,
    votes2: 0,
    user_id: '',
}
```

## Building Designer

### Building
- note: one building is only ever created for a given user, to be updated by that user later.
```js
{
    id: 1,
    left: '',
    right: '',
    middle: '',
    slogan: [''],
    user_id: '',
}
```

## Shopping Checklist

### Shopping Item
```js
{
    id: 1,
    item: '',
    quantity: 0,
    user_id: '',
}
```

## Workshop Planner

### Workshops
- because this deliverable has no way to create a workshop, you will manually enter these in the supabase dashboard
```js
{
    id: 1,
    workshop_name: '',
}
```

## Participant 
```js
{
    id: 1,
    name: '',
    user_id: '',
    // this is a one-to-many foreign_key and must be created using the "chain link" feature in the supabase dashboard
    // as a rule, let's say that, due to scheduling conflicts, we're assuming that a participant can only enroll in a single workshop, but that a single workshop will, of course, have many students enrolled.
    workshop_id: 2,
}
```

## Movie Review Site

### Movie
```
    id: 1,
    name: '',
    poster_url: '',
    year: 1999,
    genre: ''
```

### Review
```
    id: 1,
    author: '',
    rating: 2,
    thumbs: 'up', // or 'down' if the rating is negative
    review: '',
    // this is a one-to-many foreign_key and must be created using the "chain link" feature in the supabase dashboard
    // one review will always belong to a single movie, but one movie may have multiple reviews
    movie_id: 2,
    user_id: '',

```