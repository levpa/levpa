# How to release a new version

## Editing

- edit [README.md](./README.md) file
- put some assets into [/socials](./socials/) folder if needed

## Save, tag and release

- add changes to git staging and commit them
- if you want to release, then tag

```sh
# git add and commit
git add . && git commit -m " Readme.md fixes here "

# bump tag version
VERSION=`git describe --tags --abbrev=0 | awk -F. '{OFS="."; $NF+=1; print $0}'`
git tag -a $VERSION -m "new release $VERSION"

# push commit and tag
git push --atomic origin main $VERSION
```
