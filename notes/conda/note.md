### 기존 가상환경 설정 그대로 새 가상환경 생성

```bash
$ conda create -n [새 가상환경 이름] --clone [복사하고자 하는 가상환경 이름]
```

### 가상환경 yaml 파일 생성

```bash
$ conda env export > [새 가상환경 이름].yaml
```
