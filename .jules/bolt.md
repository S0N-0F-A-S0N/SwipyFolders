
## 2024-05-24 - [Avoid repeated MSHookIvar in loops]
**Learning:** Found that `MSHookIvar` was being called repeatedly inside `while` loops in `SwipyFolders.xm` because a helper method `getFolderIndexPathForIndex:` queried an instance variable on each invocation.
**Action:** Created a new method `getFolderIndexPathForIndex:withMaxIconCount:` that accepts the variable directly, avoiding repeated queries.
