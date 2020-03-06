# Git Submodules

## Add Submodule to repository

```bash
git submodule add url-submodule path-submodule-in-project

git submodule update --init

git submodule # Check submodule exsit

```

## Update submodule

```bash
cd path-submodule-in-project
git pull
git checkout master

cd path-project
git add path-submodule-in-project
git commit -m "Message update submodule"
```

## Remove Submodule

- Delete submodule in project

```bash
git rm --cached path-submodule-in-project
```

## Git push all submodule to remote

```bash
git submodule foreach git push
```