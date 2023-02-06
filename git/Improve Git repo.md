#git 

So, the main problem of [[00 Git]] repo is during the time the repo will grow, and on [[00 CircleCI]] side you have to clone all changes, which has been added and it'll take additional time.

So, as the solution it possible to clone repo with just latest commit, and one branch:

```bash
git clone --depth 1 [remote-repo-url] --single-branch [name]
```

Also, it possible to remove huge files from repository, a good [[00OpenSource]] tool: [BFG](https://rtyley.github.io/bfg-repo-cleaner/)
A good article how to use BFG from github: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository 