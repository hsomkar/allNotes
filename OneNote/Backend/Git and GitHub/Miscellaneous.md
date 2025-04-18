# What's the use of the staging area in Git?
 
- staging helps you split up one large change into multiple commits
- staging helps in reviewing changes
- staging helps when a merge has conflicts -
- staging helps you keep extra local files hanging around -
- staging helps you sneak in small changes
 
# What is Git stash?
 
- git stash temporarily shelves (or stashes) changes you've made to your working copy so you can work on something else, and then come back and re-apply them later on. Stashing is handy if you need to quickly switch context and work on something else, but you're mid-way through a code change and aren't quite ready to commit.
 
# Git tag
 
- Tags are ref's that point to specific points in Git history. Tagging is generally used to capture a point in history that is used for a marked version release (i.e. v1.0.1). A tag is like a branch that doesn’t change. Unlike branches, tags, after being created, have no further history of commits.
 
# head
 
- You can think of the HEAD as the "current branch". When you switch branches with
    
    ```
    git checkout
    
    
    origin
    
    
    ```
    
    , the HEAD revision changes to point to the tip of the new branch.
 
# origin
 
- origin is the default **alias** to the URL of your remote repository.
- We can change this **alias**
