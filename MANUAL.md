# GitHub Pages Daily Insights 작업 이해 매뉴얼

이 문서는 `jseongchoi.github.io` 저장소에 만든 Daily Insights 블로그가
어떤 흐름으로 만들어졌고, 앞으로 어떻게 운영하면 되는지 이해하기 위한 기록입니다.

## 1. 목표를 정했다

처음 목표는 단순했습니다.

하루에 인사이트 하나를 짧게 정리하고, 그것을 GitHub Pages에 올려서 개인 지식 기록으로 쌓는 것입니다.

즉, 이 프로젝트는 거창한 블로그 시스템이 아니라 아래 흐름을 쉽게 만들기 위한 저장소입니다.

```text
오늘 배운 점 정리
→ Markdown 파일 하나 작성
→ GitHub에 commit/push
→ GitHub Pages 사이트에 자동 반영
```

## 2. GitHub Pages용 저장소를 만들었다

GitHub에 아래 저장소를 만들었습니다.

```text
jseongchoi/jseongchoi.github.io
```

GitHub Pages에는 특별한 규칙이 있습니다.

GitHub 사용자명이 `jseongchoi`일 때 저장소 이름을 아래처럼 만들면:

```text
jseongchoi.github.io
```

GitHub가 자동으로 아래 주소의 웹사이트로 연결해줍니다.

```text
https://jseongchoi.github.io
```

그래서 이 저장소는 단순 코드 저장소이면서 동시에 웹사이트의 원본이 됩니다.

## 3. Jekyll 구조를 넣었다

GitHub Pages는 기본적으로 Jekyll이라는 정적 사이트 생성기를 지원합니다.

Jekyll은 쉽게 말해 Markdown 파일을 HTML 블로그 페이지로 바꿔주는 도구입니다.

직접 HTML을 매번 만들 필요 없이, 아래처럼 Markdown으로 글을 쓰면:

```md
# 오늘의 인사이트

Codex는 매일 생각을 정리하는 루틴 도구로 쓸 수 있다.
```

GitHub Pages가 배포 과정에서 웹페이지로 변환합니다.

현재 저장소에는 Jekyll이 이해할 수 있는 기본 파일들이 들어 있습니다.

```text
_config.yml
index.md
about.md
_posts/
_drafts/
README.md
MANUAL.md
```

## 4. 각 파일의 역할을 정했다

현재 핵심 파일의 역할은 다음과 같습니다.

```text
_config.yml
```

사이트 제목, 설명, 테마 같은 기본 설정을 담습니다.

```text
index.md
```

사이트 첫 화면입니다. Jekyll의 `home` 레이아웃을 사용해서 글 목록을 보여줍니다.

```text
about.md
```

블로그 소개 페이지입니다.

```text
_posts/
```

실제로 공개되는 글을 넣는 폴더입니다.

```text
_drafts/
```

아직 공개하지 않는 초안이나 글 템플릿을 넣는 폴더입니다.

```text
README.md
```

저장소를 처음 봤을 때 빠르게 이해하기 위한 짧은 설명입니다.

```text
MANUAL.md
```

지금 읽고 있는 문서입니다. 작업 흐름을 기술적으로 이해하기 위한 매뉴얼입니다.

## 5. 첫 번째 글을 만들었다

첫 글은 아래 파일입니다.

```text
_posts/2026-05-07-daily-insight-routine.md
```

Jekyll에서 블로그 글 파일명은 보통 아래 규칙을 따릅니다.

```text
YYYY-MM-DD-title.md
```

예를 들면:

```text
2026-05-07-daily-insight-routine.md
```

이 파일은 2026년 5월 7일에 작성한 `daily-insight-routine`이라는 글이라는 뜻입니다.

글 파일 맨 위에는 front matter라는 설정 영역이 있습니다.

```md
---
layout: post
title: "하루에 인사이트 하나씩 쌓기"
date: 2026-05-07 20:00:00 +0900
categories: insight
tags: [codex, writing, github-pages]
---
```

이 부분은 글 제목, 날짜, 태그, 레이아웃을 Jekyll에게 알려주는 역할을 합니다.

그 아래부터는 일반 Markdown 본문입니다.

## 6. 글 템플릿을 만들었다

매일 새 글을 쓸 때 처음부터 형식을 고민하지 않도록 템플릿을 만들었습니다.

```text
_drafts/insight-template.md
```

앞으로 새 글을 쓸 때는 이 파일의 구조를 참고하면 됩니다.

권장 글 구조는 단순합니다.

```text
한 줄
왜 흥미로웠나
내 일에 적용하면
관련 링크나 메모
```

목표는 긴 글을 쓰는 것이 아니라, 매일 하나의 생각을 부담 없이 남기는 것입니다.

## 7. GitHub에 commit/push했다

로컬에서 파일을 만든 뒤 GitHub 저장소에 올렸습니다.

작업 흐름은 기술적으로 아래와 같습니다.

```text
파일 생성 또는 수정
→ git add
→ git commit
→ git push
```

GitHub Pages는 `main` 브랜치에 변경사항이 올라오면 자동으로 사이트를 다시 빌드합니다.

즉, 매번 수동으로 배포 버튼을 누르는 방식이 아니라 GitHub에 push하면 배포가 시작됩니다.

## 8. 사이트가 배포되는지 확인했다

GitHub Pages 사이트 주소는 아래입니다.

```text
https://jseongchoi.github.io
```

첫 글은 아래 주소 형태로 공개됩니다.

```text
https://jseongchoi.github.io/2026/05/07/daily-insight-routine/
```

중간에 한 가지 이슈가 있었습니다.

Jekyll은 글의 `date`가 현재 시간보다 미래이면 그 글을 아직 공개하지 않습니다.

처음에는 글 시간이 미래로 잡혀서 첫 글이 안 보였고, 시간을 현재보다 과거로 수정해서 다시 push했습니다.

## 9. 현재 작업공간으로 이어왔다

처음 작업은 다른 Codex 작업 폴더에서 진행되었습니다.

이후 현재 작업공간인 아래 경로에서 이어서 작업할 수 있도록 저장소를 clone했습니다.

```text
C:\Users\jiseong\Documents\Python\githubio
```

현재 이 폴더가 `jseongchoi.github.io` 저장소의 로컬 작업공간입니다.

앞으로는 이 폴더에서 글을 추가하고 commit/push하면 됩니다.

## 10. 앞으로 매일 글을 추가하는 방법

매일 새 인사이트를 올리는 기본 흐름은 아래와 같습니다.

1. `_posts` 폴더에 새 파일을 만듭니다.
2. 파일명은 `YYYY-MM-DD-title.md` 형식으로 정합니다.
3. 파일 맨 위에 front matter를 작성합니다.
4. 그 아래에 Markdown으로 본문을 씁니다.
5. git commit을 만듭니다.
6. GitHub에 push합니다.
7. 잠시 후 `https://jseongchoi.github.io`에서 확인합니다.

예시 파일명:

```text
_posts/2026-05-08-ai-workflow.md
```

예시 글:

```md
---
layout: post
title: "AI와 함께 일하는 방식"
date: 2026-05-08 09:00:00 +0900
categories: insight
tags: [ai, workflow]
---

## 한 줄
AI는 답을 대신 내는 도구라기보다, 생각을 더 빨리 정리하게 도와주는 동료에 가깝다.

## 왜 흥미로웠나
혼자 생각하면 막히는 부분도 대화하면서 구조화하면 훨씬 빨리 정리된다.

## 내 일에 적용하면
아이디어, 코드, 문서 작업을 시작할 때 먼저 초안을 만들고 다듬는 방식으로 활용할 수 있다.
```

## 11. 기억해야 할 핵심

이 프로젝트에서 가장 중요한 개념은 세 가지입니다.

```text
GitHub repo = 사이트 원본 저장소
```

```text
Markdown file = 블로그 글
```

```text
git push = 사이트 배포 트리거
```

결국 해야 할 일은 복잡하지 않습니다.

매일 `_posts`에 Markdown 파일 하나를 추가하고 GitHub에 올리면 됩니다.
