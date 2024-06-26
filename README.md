# mkdocstrings labels

Use the following command to clone labels from this repository into another:

```bash
gh label clone -f mkdocstrings/github-labels -R mkdocstrings/python
```

Shell commands to apply labels to all repositories within @mkdocstrings (except a few):

```bash
for repo in $(gh repo list mkdocstrings --json name --jq '.[].name' --limit 100 | grep -ve github -e vba -e crystal); do
  gh label clone -f mkdocstrings/github-labels -R mkdocstrings/$repo
done
```
