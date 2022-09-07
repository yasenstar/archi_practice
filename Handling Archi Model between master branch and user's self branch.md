



```sequence
Title: Handling Archi Model between "master" branch and user's self branch
User(Local)->User(Local): Working on self branch, Commit
Note left of User(Local): [Current]
User(Local)->User(Remote): Publish to User branch repo
User(Local)->Master(Local): Switch to
Note left of Master(Local): [Current]
Master(Remote)->Master(Local): Manually refreshing ([Collabortion]->[Refresh Model])
Master(Local)->User(Local): Switch back to User(Local)
Note left of User(Local): [Current]
Master(Local)->User(Local): Merge Branch into Current Branch, choose "Local"
User(Local)->User(Local): if Merging issue, fix problem with colleagues
User(Local)->User(Remote): Publish user branch after local merging
User(Local)->Master(Local): Switch to
Note left of Master(Local): [Current]
User(Local)->Master(Local): Merge Branch into Current Branch, choose "Local"
Note left of Master(Local): this step is safe!
Master(Local)->Master(Remote): Publish master branch after local merging
```



