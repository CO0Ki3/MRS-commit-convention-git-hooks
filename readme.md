- 만약 권한이 없다면
```console
chmod ug+x .git/hooks/prepare-commit-msg
```

- 커밋이 잘 들어갔나 확인

```console
git log --branches --not --remotes
```

- 바로 이전 푸시전인 커밋 취소

```console
git reset --soft HEAD^  
```
