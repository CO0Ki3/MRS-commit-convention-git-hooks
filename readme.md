## Prefix가 붙는 조건
1. 브랜치 명이 MRS-00000 꼴이면서, 커밋 메시지에 [MRS-00000]이 없는 경우
2. 브랜치 명이 MRS-00000 꼴이 아니면서, 커밋 메시지에 [MRS-00000]이 없는 경우
> 2번 경우에는 [MRS-00000] prefix가 붙게 됩니다.

<br>

-------
<br>

## 적용 시 필요할지도 모르는 커멘트 모음
- 만약 권한이 없다면
```console
chmod ug+x .git/hooks/prepare-commit-msg
```

- 만약 권한을 주었는데 실행이 안된다면
```
git config --local core.hooksPath .git/hooks
```

- 커밋이 잘 들어갔나 확인

```console
git log --branches --not --remotes
```

- 바로 이전 푸시전인 커밋 취소

```console
git reset --soft HEAD^  
```
