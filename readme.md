## Prefix가 붙는 조건
1. 브랜치 명이 NMRS-숫자 꼴이면서, 커밋 메시지에 [NMRS-숫자]이 없는 경우
2. 브랜치 명이 NMRS-숫자 꼴이 아니면서, 커밋 메시지에 [NMRS-숫자]이 없는 경우
> 2번 경우에는 [NMRS-00000] prefix가 붙게 됩니다.

### Example
> *branch : feature/NMRS-12345*<br>
> *msg / feature: somethong*
>> [NMRS-12345] feature: somethong<br>
---
> *branch : feature/NMRS-12345*<br>
> *msg / [NMRS-54321] feature: somethong*
>> [NMRS-54321] feature: somethong<br>
---
> *branch : develop*<br>
> *msg / feature: somethong*
>> [NMRS-00000] feature: somethong<br>
---
> *branch : hotfix/0.0.1*<br>
> *msg / [NMRS-12345] feature: somethong*
>> [NMRS-12345] feature: somethong<br>
---
> *branch : feature/NMRS-12345*<br>
> *msg / NMRS-12345 feature: somethong*
>> [NMRS-12345] NMRS-12345 feature: somethong<br>


-------
<br>

## 적용 시 필요할지도 모르는 커멘트 모음
- 만약 권한이 없다면
```console
chmod ug+x .git/hooks/*
```

- 만약 권한을 주었는데 실행이 안된다면
```console
git config --local core.hooksPath .git/hooks
git config advice.ignoredHook false
```

- 커밋이 잘 들어갔나 확인

```console
git log --branches --not --remotes
```

- 바로 이전 푸시전인 커밋 취소

```console
git reset --soft HEAD^  
```
