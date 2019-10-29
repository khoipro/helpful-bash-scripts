# Git Tips

## Clear any existing repositories excerpt "origin"

This issue happens several times when trying to deploy from single GitLab repository to multiple Pantheon sites. Sometimes it said repository exists, sometimes no, so we must check and remove each from repository list before proceed.

```bash
echo -e "Clear any existing repo excerpt origin"
git remote | while read line; do
  if [[ $line != 'origin' ]]; then
    echo -e "Remove remote repo $line"
    git remote remove $line
  fi
done
```
