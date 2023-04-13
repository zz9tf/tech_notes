

# push to multiple remote repo

From [link](https://stackoverflow.com/questions/5785549/able-to-push-to-all-git-remotes-with-the-one-command)

```
# Create an all remote with several repo URLs to its name
git remote add all repo_URL1
git remote set-url --add all repo_URL2
git remote set-url --add all repo_URL3

# Then to push
git push all --all
```

You can view the details in ```.git/config```:

```
  [remote "all"]
  url = repo_URL1
  url = repo_URL2
  url = repo_URL3
```

