
# Lecture 5 - Fetching and Supabase

## Supabase dashboard

## Async/Await and Fetching in supabase

## fetch-utils.js

```js
const SUPABASE_URL = 'https://gxwgjhfyrlwiqakdeamc.supabase.co';
const SUPABASE_KEY = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJyb2xlIjoiYW5vbiIsImlhdCI6MTYzNjQxMTMxMiwiZXhwIjoxOTUxOTg3MzEyfQ.PHekiwfLxT73qQsLklp0QFEfNx9NlmkssJFDnlvNIcA';

const client = supabase.createClient(SUPABASE_URL, SUPABASE_KEY);
```
## The 'load' event

```js
window.addEventListener('load', async () => {
    const response = await fetchData();
});
```

## Query Params