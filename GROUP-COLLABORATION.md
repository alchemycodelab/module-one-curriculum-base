# Spring Week Kickoff

## Manage access

Here's how you can add people as collaborators to your project. This way, they can make PRs to the group repo.

![](./assets/manage-access.png)

You'll also want to create a new organization for supabase and invite everybody to it.
![image](https://user-images.githubusercontent.com/16160135/149395484-304cb6fd-08f1-4bb9-ba4f-bb079442dbbd.png)


## Branch protection rules

Here's how you can protect your `main` branch from unruly 'cowboy coding'. If you set up these rules, you cannot push directly to main, and you cannot merge a PR without at least 3 approvals.1

![](./assets/branch-protection-1.png)
![](./assets/branch-protection-2.png)

## Merge conflict exercise

- Merge conflicts are inevitable. They not a bad thing.
> Merge conflicts in git happen when two branches were changed on the same line or in the same content of a file before a merge. If you just extend a file or append something, git usually just figures it out by itself. (https://stackoverflow.com/questions/33454605/intentionally-create-merge-conflict)

- Here's what a merge conflict looks like in VSCode:

![](./assets/merge-conflict.png)

- When you get a merge conflict, simply choose to `Accept incoming change`, `Accept current change`, or `Accept both changes`. Make additional final changes if necessary, then make a commit to lock the decision in.

- Repeat the following exercise until everybody has participated at least once, either as Coder A or Coder B.

### How to create a merge conflict on purpose:
0) Make a repo called "merge-conflict-practice". Add collaborators.
1) Everybody start by cloning down that repo. Do this at the beginning or you won't get a merge conflict.
2) Coder A makes a `new` branch.
    - Coder A makes a change and a commit on line 1 of `app.js` in their `new` branch.
    - Coder A pushes their code and makes a PR from `new` to `main`.
    - this PR gets merged into main.
3) Meanwhile, Coder B _forgets_ to `git pull origin main`!
4) Coder B creates create a new branch (i.e. `my-branch`).
    - Coder B makes a change and a commit on line 1 of `app.js` in their `main` branch. This is the same line as Coder A.
    - Coder B pushes their code and makes a PR from `my-branch` to `main`.
    - Notice the PR tells you there is a conflict!
    - Coder B pulls the freshest code from `main`, which now has Coder A's commit: `git pull origin main`
    - Coder B resolves the merge conflict, then ACP to their `my-branch` branch.
    - Notice the PR tells you you can merge (no conflict!).
    - Merge the PR and repeat with a new Coder B.

# Team Questions
1) What is our collaboration plan? How will we decide which features make it into the app? How will we organize and prioritize features? Will we use Miro, or some other group collaboration tool? How will we decide who works on what feature? How will we decide which features are best for mob or pair or individual work? How will we merge code into the main branch? What is our code review process?
2) What will we do when a conflict comes up? When do we decide to ask for outside help?
3) How will we make sure that we do not reproduce in this sprint group the patterns that have historically excluded people from marginalized groups from feeling safe, seen, and valued in tech work?
4) Given that the best projects are generally produced by the teams who have the most fun, how can we 'keep it light'? What can we do to make sure we look back fondly on this special week? When will we hold our code-free feelings check-ins?
5) How did the merge conflict exercise go?
6) What tables need to be set up in supabase? What properties do they need? Do any of these tables have relationships to one another? If so, what are the foreign and primary keys? Plan all of this out before building the tables in supabase.
