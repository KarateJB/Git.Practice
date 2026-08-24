# Git Practice

## Submodules

### Path: ./submodules/GitPracticeSub/

Git repo: https://github.com/TheForceJB/GitPracticeSub

To initialize submodules and checkout `master` branch after forking:
```bash
git submodule update --init --remote

cd submodules/GitPracticeSub/
git checkout master
```

Or initialize the submodules and checkout Gitlink SHA after forking:
```bash
git submodule update --init

cd submodules/GitPracticeSub/
git checkout test
```

Pull or push changes to the remote TheForeceJB/GitPracticeSub when at the submodule path.


PS. The submodule was added by this command:
```bash
git submodule add git@github.com:TheForceJB/GitPracticeSub.git submodules/GitPracticeSub
```

## Subtrees

The following two subtrees are from the same remote repository, initialize the remote name `sub` after you fork this main repo:
```bash
git remote add sub git@github.com:TheForceJB/GitPracticeSub.git
```

### Path: ./subtrees/GitPracticeSub/

Git repo: https://github.com/TheForceJB/GitPracticeSub
Remote name: sub
Branch: master

To pull changes:
```bash
git fetch sub

git subtree pull \
  --prefix=subtrees/GitPracticeSub \
  sub \
  master \
  --squash
```

To push changes:
```bash
git subtree push \
  --prefix=subtrees/GitPracticeSub \
  sub \
  master
```

PS. The subtree was added by this command:
```bash
git remote add sub git@github.com:TheForceJB/GitPracticeSub.git
git fetch sub
git subtree add \
  --prefix=subtrees/GitPracticeSub \
  sub \
  master \
  --squash
```

### Path: ./subtrees/Demo/

Git repo: https://github.com/TheForceJB/GitPracticeSub (only on path: ./demo/)
Remote name: sub-demo
Branch: master

To pull changes:
```bash
git fetch sub-demo

git subtree pull \
  --prefix=subtrees/GitPracticeSub/Demo \
  sub-demo \
  master \
  --squash
```

To push changes:
```bash
git subtree push \
  --prefix=subtrees/GitPracticeSub/Demo \
  sub-demo \
  master
```

PS. The subtree was added by this command:
```bash
git fetch sub
git subtree add \
  --prefix=subtrees/GitPracticeSub/Demo \
  sub \
  master:demo \
  --squash
```


